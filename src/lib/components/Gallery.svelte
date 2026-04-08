<script>
    import '../../app.css'
    import { onMount } from 'svelte'
    let { images } = $props()
    let els = []
    let current = $state(1)
    let mobile = $state(false)

    const extended = $derived([images[images.length - 1], ...images, images[0]])

    onMount(() => {
        const mq = window.matchMedia('(max-width: 650px)')
        mobile = mq.matches
        mq.addEventListener('change', e => mobile = e.matches)

        if (mobile) {
            els[1].scrollIntoView({ behavior: 'instant', block: 'nearest', inline: 'center' })
        }
    })

    function prev() {
        current -= 1
        els[current].scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' })
        if (current === 0) {
            setTimeout(() => {
                current = images.length
                els[current].scrollIntoView({ behavior: 'instant', block: 'nearest', inline: 'center' })
            }, 300)
        }
    }

    function next() {
        current += 1
        els[current].scrollIntoView({ behavior: 'smooth', block: 'nearest', inline: 'center' })
        if (current === extended.length - 1) {
            setTimeout(() => {
                current = 1
                els[current].scrollIntoView({ behavior: 'instant', block: 'nearest', inline: 'center' })
            }, 300)
        }
    }
</script>

<div class="gallery" id="gallery">
    <h2>GALLERY</h2>

    <div class="carousel">
        <div class="container">
            {#each (mobile ? extended : images) as image, i}
                <div bind:this={els[i]}>
                    <img src={image} alt="">
                    <div class="caption">
                        <p>caption</p>
                    </div>
                </div>
            {/each}
        </div>

        <div class="arrows">
            <button onclick={prev}>&lt;</button>
            <button onclick={next}>&gt;</button>
        </div>
    </div>
</div>

<style>
    .gallery {
        padding: 2rem;
        background: var(--black) radial-gradient(circle, rgba(50,50,50,0.3) 1px, transparent 1px);
        background-size: 20px 20px;
        background-attachment: fixed;
        background-position: center;
    }

    h2 {
        font-family: 'Cormorant', serif;
        font-size: 1.5rem;
        margin-bottom: 1rem;
        letter-spacing: 2px;
        color: var(--light-grey);
    }

    .carousel {
        display: contents;
    }

    .container {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        grid-template-rows: repeat(2, 1fr);
        gap: 4px;
    }

    .container > div {
        position: relative;
        width: fit-content;
        height: fit-content;
    }

    .container > div:first-child {
        grid-column: span 2;
        grid-row: span 2;
    }

    .container img {
        display: block;
        border: 2px solid var(--gold);
    }

    .caption {
        opacity: 0;
        transition: all 1s cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .container > div:hover .caption {
        opacity: 1;
    }

    p {
        position: absolute;
        bottom: 2px;
        left: 2px;
    }

    .arrows {
        display: none;
    }

    @media (max-width: 650px) {
        .carousel {
            display: block;
            position: relative;
        }

        .container {
            display: flex;
            flex-direction: row;
            flex-wrap: nowrap;
            overflow: hidden;
        }

        .container > div {
            min-width: 100%;
            flex-shrink: 0;
        }

        .arrows {
            display: flex;
            justify-content: space-between;
            position: absolute;
            top: 50%;
            left: 0; right: 0;
            transform: translateY(-50%);
            z-index: 1;
            pointer-events: none;
        }

        .arrows button {
            pointer-events: all;
            font-size: 4rem;
            background: none;
            border: none;
            color: var(--gold);
            cursor: pointer;
        }
    }
</style>