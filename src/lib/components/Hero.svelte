

<script>
	import '../../app.css';
    let { images } = $props()
</script>

<div class="hero" id="about">
<div class="about">
    <div class="intro">
        <div>
            <h1>Karate,<br> outdoors</h1>
            <p>Traditional karate taught in the open air, four times a week at the park. All levels welcome.</p>
        </div>

        <a href="#join" class="join">JOIN A CLASS</a>
    </div>
    <div class="images">
        <img src={images[0]} alt="">
        <img src={images[1]} alt="">
        <img src={images[2]} alt="">
    </div>
</div>

    <div class="wide-container">
    <hr>
    <div class="info-container">
        <div class="info">
            <h2>5+</h2>
            <p>YEARS TRAINING</p>
        </div>
        <div class="info">
            <h2>60+</h2>
            <p>STUDENTS</p>
        </div>
        <div class="info">
            <h2>4x</h2>
            <p>CLASSES WEEKLY</p>
        </div>
    </div>
    </div>
</div>

<style>
    .hero {
        height: fit-content; 
        gap: 24px; 
        padding: 3rem;
        margin-top: 2rem;
    }

    .about {
        width: 100%;
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        margin-bottom: 2rem;
    }

    .intro {
        display: flex;
        flex-direction: column;
        gap: 1rem;
        max-width: 300px;
        margin-top: 2rem;
    }

    .intro h1 {
        font-family: 'Cormorant', serif;

    }

    p {
        font-size: 1rem;
        font-weight: 100;
        line-height: 1.9;
        color: var(--light-grey);
    }

    h1 {
        font-size: 4rem;
        line-height: 1.2;
    }
    h2 {
        font-size: 2.5rem;
        letter-spacing: 2px;
        color: var(--gold);
    }

    .join {
        width: fit-content;
        background-color: var(--black);
        border: 1px solid var(--gold);
        padding: 0.5rem;
        font-size: 1rem;
        color: var(--white);
    }

    .images {
        display: grid;
        align-self: center;
        justify-content:flex-end;
        grid-template-columns: 300px 300px;
        grid-template-rows: 112.5px 112.5px;
        gap: 6px;
    }

    .images img {
        width: 300px;
        border: 1px solid var(--gold);
    }

    .images img:first-child {
        grid-row: span 2;
    }

    .wide-container {
        grid-column: span 2;
    }

    hr {
        border-width: 1.5px;
        color: rgba(0, 0, 0, 0.2);
    }

    .info-container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        margin-top: 2rem;
    }

    .info-container h2 {
        font-size: clamp(1rem, 0.5rem + 2vw, 2.5rem);
    }

    .info-container p {
        font-size: clamp(0.5rem, 0.25rem + 1.5vw, 1rem);
    }

    .info {
        text-align: center;
        margin: 0;
        padding: 0;
    }

    .info:not(:last-child) {
        margin-right: 15%;
        padding-right: 15%;
        border-right: 1px solid var(--light-gold);
    }

    @media (max-width: 1024px) {
        .about {
            flex-direction: column;
            gap: 2rem;
        }
    }

    @media (max-width: 650px) {
        .images {
            grid-template-columns: 300px;
            grid-template-rows: 112.5px 112.5px 112.5px;
            align-self: self-start;
        }
    }
</style>