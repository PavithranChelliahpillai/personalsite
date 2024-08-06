<script>
    // @ts-nocheck

    import { onMount } from "svelte";
    import { fly, blur, fade } from "svelte/transition";
    import { backOut, cubicInOut, sineInOut } from "svelte/easing";
    const words = ["Meet", "your", "next", "software", "engineer."];
    const stunnings = ["stunning", "stunning", "stunning"];
    let ready = false;
    // @ts-ignore
    import IntersectionObserver from "svelte-intersection-observer";
    import Navbar from "./template/nav.svelte";
    import MediaQuery from "./MediaQuery.svelte";

    onMount(() => {
        setTimeout(() => {
            ready = true;
        }, 500);
    });
    // @ts-ignore
    let elem1, elem2;
    /**
     * @type {HTMLDivElement}
     */
    let y;
    /**
     * @type {HTMLDivElement}
     */
    let elem3;
    let elem4;
    let elem5;
    let elem6;
    let elem7;
    let elem8;
    $: outerWidth = 0;
    $: innerWidth = 0;
    $: outerHeight = 0;
    $: innerHeight = 0;
</script>

<svelte:window
    bind:innerWidth
    bind:outerWidth
    bind:innerHeight
    bind:outerHeight
    bind:scrollY={y}
/>

<svelte:head>
    <title>Pavithran Chelliahpillai</title>
    <meta name="description" content="Pavithran's personal website and online portfolio.">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta charset="utf-8">
    <link rel="canonical" href="https://pchelliahpillai.com">
    <meta property="og:title" content="Pavithran Chelliahpillai">
    <meta property="og:description" content="Pavithran's personal website and online portfolio.">
    <meta property="og:url" content="https://pchelliahpillai.com">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Pavithran Chelliahpillai">
    <meta name="twitter:description" content="Pavithran's personal website and online portfolio.">
</svelte:head>

<body>
    <div id="title" class="flexbox">
        {#each words as word, i}
            {#if ready}
                <h1
                    in:fly={{
                        delay: 200 * i,
                        duration: 500,
                        easing: cubicInOut,
                        y: 30,
                    }}
                    class={word == "software" || word == "engineer."
                        ? "shine"
                        : ""}
                >
                    {word}
                </h1>
            {/if}
        {/each}
    </div>

    {#if ready}
        <div id="webdev" bind:this={elem1}>
            <IntersectionObserver once element={elem1} let:intersecting>
                <div class="flexbox">
                    <div class="child">
                        {#if intersecting}
                            <h1
                                style="margin-top: 0;"
                                transition:fly={{
                                    delay: 1000,
                                    duration: 1000,
                                    x: -100,
                                }}
                            >
                                Intersecting
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 1250,
                                    duration: 1000,
                                    x: -100,
                                }}
                            >
                                stunning
                            </h1>
                        {/if}
                        {#each stunnings as word, i}
                            {#if intersecting}
                                <h1
                                    transition:fly={{
                                        delay: 200 * i + 1350,
                                        duration: 500,
                                        easing: cubicInOut,
                                        y: -100,
                                    }}
                                    class="stunning"
                                    id="s{i}"
                                >
                                    {word}
                                </h1>
                            {/if}
                        {/each}
                        {#if intersecting}
                            <h1
                                transition:fly={{
                                    delay: 2000,
                                    duration: 1000,
                                    x: -100,
                                }}
                            >
                                interface
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 2250,
                                    duration: 1000,
                                    x: -100,
                                }}
                            >
                                design...
                            </h1>
                        {/if}
                    </div>
                    <div class="child" id="jobs">
                        {#if intersecting}
                            <a
                                class="show"
                                id="pair"
                                transition:blur={{
                                    delay: 2500,
                                    duration: 1000,
                                }}
                                href="https://principleair.pages.dev"
                                target="_blank"
                                style="color: inherit;"
                            >
                                <h2>Principle Air Systems</h2>
                            </a>
                            <a
                                class="show"
                                id="kanda"
                                transition:blur={{
                                    delay: 3000,
                                    duration: 1000,
                                }}
                                href="https://kanthavanamtemple.com"
                                target="_blank"
                                style="color: inherit;"
                            >
                                <h2>Kanthavanam</h2>
                            </a>
                        {/if}
                    </div>
                </div>
            </IntersectionObserver>
        </div>
    {/if}
    {#if ready}
        <div id="algo" bind:this={elem2}>
            <IntersectionObserver once element={elem2} let:intersecting>
                <div class="flexbox" id="badp">
                    <div class="child" id="jobs">
                        {#if intersecting}
                            <a
                                class="show"
                                id="lego"
                                transition:blur={{
                                    delay: 2500,
                                    duration: 1000,
                                }}
                                href="https://github.com/PavithranChelliahpillai/legoify"
                                target="_blank"
                                style="color: inherit;"
                            >
                                <h2>LEGOify</h2>
                            </a>
                        {/if}
                    </div>
                    <div class="child" id="badboy" style="padding: 5vh">
                        {#if intersecting}
                            <h1
                                style="margin-top: 0;"
                                transition:fly={{
                                    delay: 1000,
                                    duration: 1000,
                                    x: 100,
                                }}
                            >
                                With
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 1250,
                                    duration: 1000,
                                    x: 100,
                                }}
                                style="color: #309cad"
                            >
                                algorithms,
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 1500,
                                    duration: 1000,
                                    x: 100,
                                }}
                                style="color: #86e0d7"
                            >
                                optimization,
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 1750,
                                    duration: 1000,
                                    x: 100,
                                }}
                            >
                                and
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 2000,
                                    duration: 1000,
                                    x: 100,
                                }}
                                style="color: #98bff6 "
                            >
                                computational
                            </h1>
                            <h1
                                transition:fly={{
                                    delay: 2250,
                                    duration: 1000,
                                    x: 100,
                                }}
                                style="color: #98bff6 "
                            >
                                performance
                            </h1>
                        {/if}
                    </div>
                </div>
            </IntersectionObserver>
        </div>
    {/if}
    {#if ready}
        <IntersectionObserver element={elem3} let:intersecting>
            <div
                id="final phonebye"
                style="min-height: 25vh;"
                bind:this={elem3}
            >
                    <h1
                        id="yawasaki"
                        style="right:{0.1 * y -
                            0.3 * innerHeight +
                            5}%; width:150vw;"
                    >
                        I'm excited to work with
                    </h1>
            </div>
            <div id="final phone" style="min-height: 25vh;" bind:this={elem3}>
                {#if intersecting}
                    <h1
                        id="bazinga"
                        style="right:{0.1 * y -
                            0.6 * innerHeight +
                            4}%; width:150vw;"
                    >
                        I'm excited to work with
                    </h1>
                {/if}
            </div>
        </IntersectionObserver>
        <IntersectionObserver element={elem3} let:intersecting>
            <div
                id="phonebye"
                style="height: 5vh; min-height: 60vh;"
                bind:this={elem4}
            >
                {#if intersecting}
                    <h1
                        class="shine"
                        id="youbazinga"
                        transition:fade={{ duration: 500 }}
                        style="font-size: {innerHeight / 2 +
                            (y - 3 * innerHeight) /
                                2.7}px; text-align: center; margin-top: -60vh; padding-bottom: 0; margin-bottom: 0;"
                    >
                        YOU
                    </h1>
                {/if}
            </div>
            <div
                id="phone"
                style="height: 5vh; min-height: 60vh;"
                bind:this={elem4}
            >
                {#if intersecting}
                    <h1
                        class="shine"
                        id="youbazinga"
                        transition:fade={{ duration: 500 }}
                        style="font-size: {innerHeight / 2 +
                            (y - 3.9 * innerHeight) /
                                5}px; text-align: center; margin-top: -60vh; padding-bottom: 0; margin-bottom: 0; width: 150vw; left: -25vw;"
                    >
                        YOU
                    </h1>
                {/if}
            </div>
        </IntersectionObserver>
    {/if}
    {#if ready}
        <div
            id="main"
            style="height: auto; padding-left: 1vw; justify-content: center;"
        >
            <div style="display: flex; justify-content: center;">
                <img
                    id="mememe"
                    style="height: 20vh; border: 1px solid #adc9ba; border-radius: 50%;"
                    src="/pfpimg.png"
                    alt="pfp"
                />
                <div style="padding-left: 2vw;">
                    <h2 style="font-size: 5vh; margin-bottom: 0;">
                        Pavithran Chelliahpillai
                    </h2>
                    <p id="bingbong" style="padding: 0; margin: 0; ">
                        Software Engineering at UWaterloo
                    </p>
                    <p id="bingbong" style="padding: 0; margin: 0; ">
                        Prev. at Principle Air Systems
                    </p>
                </div>
            </div>
            <!-- <div style="display: flex;">
                <hr style="height: 4px; width: 70%; margin-top: 2vh;" />
            </div> -->
            <Navbar></Navbar>
            <div
                id="bababooey"
                style="display: flex; flex-direction: column; justify-content: center; max-width: 70vw; margin-left: auto; margin-right: auto;"
            >
                <h2 style="font-size: 5vh; text-align: center;">
                    Recent Experiences
                </h2>
                <IntersectionObserver element={elem5} once let:intersecting>
                    <div bind:this={elem5}>
                        {#if intersecting}
                            <div
                                class="exp"
                                style="margin: 1vh 0.25vw; display: none;"
                                transition:fly={{
                                    delay: 500,
                                    duration: 1250,
                                    x: 200,
                                }}
                            >
                                <h2>HTS Engineering</h2>
                                <p style="margin-top: -2vh">
                                    Jun 2024 - Aug 2024
                                </p>
                                <hr />
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
                <IntersectionObserver element={elem8} once let:intersecting>
                    <div bind:this={elem8}>
                        {#if intersecting}
                            <div
                                class="exp"
                                style="margin: 1vh 0.25vw;"
                                transition:fly={{
                                    delay: 500,
                                    duration: 1250,
                                    x: 200,
                                }}
                            >
                                <h2>Narpavi Consultancy</h2>
                                <p style="margin-top: -2vh">
                                    Jan 2024 - Present
                                </p>
                                <hr />
                                <ul>
                                    <li>
                                        Developed front-end and back-end web
                                        applications and sites for companies and
                                        organizations
                                    </li>
                                    <li>
                                        Utilised HTML, CSS, and JS within a
                                        Svelte framework to create captivating
                                        websites
                                    </li>
                                    with heavily optimised, high performance code
                                    <li>
                                        Portfolio of work: <a
                                            style="text-decoration: underline; color: inherit;"
                                            href="https://kanthavanamtemple.com"
                                            target="_blank">Kanthavanam</a
                                        >,
                                        <a
                                            style="text-decoration: underline; color: inherit;"
                                            href="https://principleair.pages.dev"
                                            target="_blank"
                                            >Principle Air Systems</a
                                        >
                                    </li>
                                </ul>
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
                <IntersectionObserver element={elem6} once let:intersecting>
                    <div bind:this={elem6}>
                        {#if intersecting}
                            <div id="bruh" style="display: flex;">
                                <div
                                    class="exp"
                                    transition:fly={{
                                        delay: 700,
                                        duration: 1250,
                                        x: -1000,
                                    }}
                                    style="margin: 1vh 0.25vw;"
                                >
                                    <h2>TrainTrack</h2>
                                    <p style="margin-top: -2vh">
                                        Personal Project
                                    </p>
                                    <hr />
                                    <ul>
                                        <li>
                                            Developed a webapp to back-test
                                            user-created strategies through
                                            artificial intelligence
                                        </li>
                                        <li>
                                            Recognizes distinctions in price
                                            action between technical
                                            (chart-based) analysis and
                                            fundamental (event/news-based)
                                            analysis at a high degree
                                        </li>
                                        <li>
                                            Utilizes a C++ stack with Armadillo
                                            as the main artificial intelligence
                                            library for efficiency, coupled with
                                            a React frontend
                                        </li>
                                    </ul>
                                </div>
                                <div
                                    class="exp"
                                    transition:fly={{
                                        delay: 700,
                                        duration: 1250,
                                        x: 1000,
                                    }}
                                    style="margin: 1vh 0.25vw;"
                                >
                                    <h2>Principle Air Systems</h2>
                                    <p style="margin-top: -2vh">
                                        Jul 2022 - Jul 2024
                                    </p>
                                    <hr />
                                    <ul>
                                        <li>
                                            Assisted HVAC engineers with
                                            creating technical and shop drawings
                                            of buildings’ systems
                                        </li>
                                        <li>
                                            Gained technical knowledge of air
                                            systems, and the importance of the
                                            design process when planning a
                                            building’s layout
                                        </li>
                                        <li>
                                            Applied programming expertise in
                                            automotive programming systems
                                            across large-scale projects
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
                <IntersectionObserver element={elem7} once let:intersecting>
                    <div bind:this={elem7}>
                        {#if intersecting}
                            <div id="bruh" style="display: flex;">
                                <div
                                    class="exp"
                                    transition:fly={{
                                        delay: 700,
                                        duration: 1250,
                                        x: -1000,
                                    }}
                                    style="margin: 1vh 0.25vw;"
                                >
                                    <h2>LEGOify</h2>
                                    <p style="margin-top: -2vh">
                                        Personal Project
                                    </p>
                                    <hr />
                                    <ul>
                                        <li>
                                            App designed to allow users to take
                                            a picture of any item and instantly
                                            receive pictorial instructions on
                                            how to create a 3-D LEGO model of
                                            that object
                                        </li>
                                        <li>
                                            Utilizes photogrammetry artificial
                                            intelligence technology
                                        </li>
                                        <li>
                                            Applied a divide-and-conquer
                                            algorithm with dynamic programming
                                            techniques to optimize solutions for
                                            large scale models
                                        </li>
                                    </ul>
                                </div>
                                <div
                                    class="exp"
                                    transition:fly={{
                                        delay: 700,
                                        duration: 1250,
                                        x: 1000,
                                    }}
                                    style="margin: 1vh 0.25vw;"
                                >
                                    <h2>Oakville Swim Academy</h2>
                                    <p style="margin-top: -2vh">
                                        Feb 2023 - Jul 2024
                                    </p>
                                    <hr />
                                    <ul>
                                        <li>
                                            Instructor of semi-private and
                                            private swim classes at Oakville
                                            Swim Academy
                                        </li>
                                        <li>
                                            As an instructor, I had the
                                            privilege of working with students
                                            of all skill levels and abilities
                                            from absolute beginners to Olympic
                                            levels
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        {/if}
                    </div>
                </IntersectionObserver>
            </div>
        </div>
        <div style="height: 1vh;"></div>
    {/if}
</body>

<MediaQuery query="(max-width: 1000px)" let:matches>
    {#if matches}
        <style>
            #yawasaki {
                letter-spacing: -2px !important;
            }
            #youbazinga {
                padding-top: 20vh !important;
            }
            .flexbox {
                display: block !important;
            }
            .child h1 {
                font-size: 17vw !important;
            }
            #badp {
                display: flex !important;
                flex-direction: column-reverse !important;
            }
            #badboy {
                padding: 0 !important;
            }
            .show {
                padding-top: 10vh !important;
            }
            #ray {
                margin-top: 1vh !important;
                padding-top: 0 !important;
            }
            #webdev {
                height: auto !important;
                min-height: 50vh !important;
            }
            h1 {
                line-height: 12vh !important;
            }
            #title h1 {
                font-size: 20vw !important;
                line-height: 13vh !important;
            }
            #title {
                width: 80% !important;
                padding-left: 5vw !important;
                padding-bottom: 13vh !important;
            }
            #bazinga {
                letter-spacing: -3px !important;
                font-size: 7vh !important;
            }
            #youbazinga {
                line-height: normal !important;
            }
            #final {
                padding: 10vh 0vw !important;
            }
            #phone {
                display: block !important;
                min-height: 40vh !important;
            }
            #phonebye {
                display: none !important;
            }
            #phone h1 {
                display: block !important;
            }
            #phoneby h1 {
                display: none !important;
            }
            #bruh {
                display: block !important;
            }
            #mememe {
                margin-top: 3vh;
            }
            p {
                font-size: 2vh !important;
            }
            #bababooey {
                max-width: 90vw !important;
            }
            #main {
                padding-top: 30vh !important;
            }
            #mememe {
                margin-top: 7vw !important;
                width: 30vw !important;
                height: auto !important;
                margin-left: 4vw;
            }
            h2 {
                font-size: 9vw !important;
            }
            #bingbong {
                font-size: 1.5vh !important;
            }
            #lego { 
                min-height: 50vh;
            }
        </style>
    {/if}
</MediaQuery>

<style>
    :global(body) {
        margin: 0;
        padding: 0;
    }
    .flexbox {
        display: flex;
        flex-direction: row;
        /* fl ex-wrap: wrap;  */
    }
    #title {
        width: 70%;
        flex-wrap: wrap;
        justify-content: center;
        margin-left: auto;
        margin-right: auto;
        height: 60vh;
        padding: 20vh 0vw;
        min-height: 70vh;
    }
    #title h1 {
        margin: 0vh 1vw;
    }
    .shine {
        background: linear-gradient(
            120deg,
            #309cad 0%,
            #86e0d7 45%,
            #98bff6 50%,
            #93d8ef 55%,
            #0c97ad 60%
        );
        -webkit-background-clip: text;
        -webkit-text-fill-color: transparent;
        animation: shine 20s linear infinite alternate;
    }

    @keyframes shine {
        0% {
            background-position: 0;
        }
        100% {
            background-position: 1000px;
        }
    }
    body {
        overflow-x: hidden;
    }
    #webdev {
        height: 100vh;
    }
    #s0 {
        color: #98bff6;
    }
    #s1 {
        color: #86e0d7;
    }
    #s2 {
        color: #309cad;
    }
    .stunning {
        margin-top: -8vh;
    }
    #webdev h1,
    #algo h1 {
        font-size: 15vh;
        margin-top: -5vh;
        margin-left: 1vw;
    }
    .child {
        flex: 0;
        flex-grow: 1;
    }
    #jobs {
        display: flex;
        flex-direction: column;
    }
    .show {
        border-radius: 2vw;
        flex: 0;
        flex-grow: 1;
        margin: 2vw;
        display: flex;
        flex-direction: column-reverse;
        padding: 0;
    }
    .show2 {
        border-radius: 2vw;
        flex: 0;
        flex-grow: 1;
        margin: 1vh 2vw;
        padding: 1vh 2vw;
        /* color: #152438; */
    }
    #kanda {
        background-image: url("/kanda.png");
        background-size: cover;
        background-position: top;
        border: 0.3vw solid #309cad;
    }
    #pair {
        background-image: url("/pair.png");
        background-size: cover;
        border: 0.3vw solid #86e0d7;
    }
    #lego {
        background-image: url("/bricks3.png");
        background-size: cover;
        border: 0.3vw solid #86e0d7;
    }
    .show h2 {
        padding: 3vh 0vw;
        padding-left: 1vw;
        font-size: 4vh;
        background-color: #1c626dcf;
        margin: 0;
        border-radius: 0vw 0vw 1.8vw 1.8vw;
    }
    #webdev {
        min-height: 110vh;
    }
    #algo {
        min-height: 100vh;
    }
    hr {
        background-color: #adc9ba;
        height: 3px;
        border: 0;
        border-radius: 30px;
    }
    #final {
        padding: 20vh 0vw;
        margin-bottom: 30vh;
        max-width: 100vw;
        max-height: 100vh;
        overflow: hidden;
    }
    #main p {
        font-size: 3vh;
    }
    .exp h2 {
        font-size: 4vh;
        margin: 2vh 0vw;
        padding: 0;
        margin-top: 1vh;
    }
    .exp {
        border-radius: 2vw;
        flex: 0;
        flex-grow: 1;
        margin: 1vh 2vw;
        padding: 1vh 2vw;
        /* color: #152438; */
        border: 1px solid #adc9ba;
    }
    .exp p {
        font-size: 2vh !important;
        width: 90%;
    }
    .exp li {
        margin-top: 2vh;
    }
    #phone h1 {
        display: none;
    }
    #phone {
        display: none;
    }
    #phonebye {
        padding-top: 20vh;
    }
    a:hover {
        filter: sepia(50);
    }
    a:hover h2 {
        filter: invert(50);
    }
    a {
        transition: all 0.3s;
    }
    h2 {
        transition: all 0.3s;
    }
</style>
