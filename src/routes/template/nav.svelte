<script>
    // @ts-ignore
    import IntersectionObserver from "svelte-intersection-observer";
    import { fly, blur, fade } from "svelte/transition";

    /**
     * @type {HTMLDivElement}
     */
    let nav;
    import MediaQuery from "../MediaQuery.svelte";
</script>

<IntersectionObserver element={nav} once let:intersecting>
    <div bind:this={nav}>
        {#if intersecting}
            <div
                class="navbar"
                transition:fly={{ delay: 200, duration: 800, x: -1000 }}
            >
                <img
                    id="favicon"
                    transition:fade={{ delay: 500, duration: 800 }}
                    src="/favicon.png"
                    alt="PC"
                />
                <ul>
                    <li
                        class="go"
                        transition:fade={{ delay: 800, duration: 800 }}
                    >
                        <a href="/resume" target="_blank">
                            <img src="res.png" alt="resume" />
                        </a>
                    </li>
                    <li
                        class="go"
                        transition:fade={{ delay: 900, duration: 800 }}
                    >
                        <a href="mailto:pchellia@uwaterloo.ca">
                            <img src="mail.png" alt="mail" />
                        </a>
                    </li>
                    <li class="go" transition:fade={{ delay: 1000, duration: 800 }}>
                        <a href="https://www.linkedin.com/in/pchellia/" target="_blank">
                            <img src="li.png" alt="linkedin" />
                        </a>
                    </li>
                    <li class="go" transition:fade={{ delay: 1100, duration: 800 }}>
                        <a href="https://github.com/PavithranChelliahpillai" target="_blank">
                            <img src="gitty.png" alt="github" />
                        </a>
                    </li>
                    <li class="go" transition:fade={{ delay: 1200, duration: 800 }}>
                        <a href="https://se-webring.xyz/" target="_blank">
                            <img src="webr.png" alt="SE Webring" />
                        </a>
                    </li>
                </ul>
            </div>
        {/if}
    </div>
</IntersectionObserver>

<MediaQuery query="(max-width: 1000px)" let:matches>
    {#if matches}
        <style>
            .navbar {
                width: 100% !important;
                margin-bottom: -4vh !important;
                margin-top: -2vh !important;
            }
            .navbar li a {
                font-size: 2vh !important;
            }
            .navbar ul {
                padding: 1vw !important;
            }
            .navbar img {
                order: 5;
                /* margin: 0vh 3vw; */
                width: 7vw !important;
            }
        </style>
    {/if}
</MediaQuery>

<style>
    .navbar:before {
        background-color: #adc9ba;
        content: "";
        display: block;
        height: 3px;
        order: 2;
        width: 100%;
    }
    .navbar {
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        width: 80%;
        margin-left: auto;
        margin-right: auto;
    }
    .navbar ul {
        display: table-row;
        list-style: none;
        align-items: center;
        justify-content: center;
    }
    .navbar a {
        padding: 2vh 2vw;
        text-decoration: none;
        border-radius: 10px;
        transition: all 0.3s ease;
        align-self: center;
        justify-self: center;
    }
    .navbar li {
        display: table-cell;
        padding: 2vh 0vw;
        margin: 0vh 0.3vw;
        text-decoration: none;
        border-radius: 10px;
        transition: all 0.3s ease;
        height: 100%;
        margin-top: auto; 
        margin-bottom: auto;
        vertical-align: middle;
    }
    .navbar #favicon {
        order: 5;
        /* margin: 0vh 3vw; */
        border: 2px solid #adc9ba;
        border-radius: 50%;
        width: 5vw;
    }
    .navbar img {
        order: 5;
        /* margin: 0vh 3vw; */
        width: 3vw;
    }
    .navbar .go:hover {
        filter: sepia(50);
    }
</style>
