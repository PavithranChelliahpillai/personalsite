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
            <div class="navbar" transition:fly={{delay: 200, duration: 800, x:-1000}}>
                <img
                    transition:fade={{ delay: 500, duration: 800 }}
                    src="/favicon.png"
                    alt="PC"
                />
                <ul>
                    <li
                        transition:fade={{ delay: 800, duration: 800 }}
                        style="margin: 10px 0px 10px 0px;"
                    >
                        <a href="/resume" target="_blank">Resume</a>
                    </li>
                    <li
                        transition:fade={{ delay: 900, duration: 800 }}
                        style="margin: 10px 0px 10px 0px;"
                    >
                        <a href="mailto:pchellia@uwaterloo.ca">Contact</a>
                    </li>
                </ul>
            </div>
        {/if}
    </div>
</IntersectionObserver>

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
        width: 60%;
        margin-left: auto;
        margin-right: auto;
    }
    .navbar ul {
        display: flex;
        list-style: none;
    }
    .navbar a {
        padding: 2vh 2vw;
        text-decoration: none;
        border-radius: 10px;
        transition: all 0.3s ease;
    }
    .navbar li { 
        padding: 2vh 0vw; 
        margin: 0vh 1vw;
        text-decoration: none;
        border-radius: 10px;
        transition: all 0.3s ease;
    }
    .navbar a {
        text-decoration: none;
        color: inherit;
        font-size: 1.5vw;
    }
    .navbar img {
        order: 5;
        /* margin: 0vh 3vw; */
        border: 2px solid #adc9ba;
        border-radius: 50%;
        width: 5vw;
    }
    .navbar li:hover {
        background: #0f1927;
    }
</style>

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
        </style>
    {/if}
</MediaQuery>
