<script>
	import '../../app.css';
</script>

<nav>
    <h1>KARATE WITH KAPIL</h1>
    <div class="nav">
        <a href="#about">ABOUT</a>
        <a href="#gallery">GALLERY</a>
        <a href="#classes">CLASSES</a>
        <a href="#join">JOIN</a>
    </div>
    <div class="collapse">
        <button>L</button>
    </div>
</nav>

<style>
    nav {
        background-color: var(--black);
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        padding: 1rem;
        position: fixed;
        top: 0;
        width: 100%;
        z-index: 1000;
        opacity: 1;

        border-bottom: 2px solid var(--gold);
        background: var(--black) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3CfeColorMatrix type='saturate' values='0'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23noise)' opacity='0.02'/%3E%3C/svg%3E");
    }

    h1 {
        color: var(--white);
        letter-spacing: 2px;
        margin-left: 2rem;
    }

    a {
        color: var(--light-grey);
        padding: 0.5rem;
        font-family: serif;
		transition: all 1s cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    a:hover {
        color: var(--white);
    }

    .collapse {
        display: none;
    }

    @media (max-width: 650px) {
        .collapse {
            display: block;
        }
    }
</style>