<script>
    import Nav from "../lib/components/Nav.svelte"
    import Hero from "../lib/components/Hero.svelte"
    import Gallery from "../lib/components/Gallery.svelte"
    import Schedule from "../lib/components/Schedule.svelte"
    import Join from "../lib/components/Join.svelte"
    import Footer from "../lib/components/Footer.svelte"
    import { base } from '$app/paths'
</script>

<div>
    <Nav></Nav>
    <Hero images={[`${base}/media/images/hero/1.png`, `${base}/media/images/hero/2.png`, `${base}/media/images/hero/3.png`]}></Hero>
    <Gallery images={[`${base}/media/images/gallery/1.png`, `${base}/media/images/gallery/2.png`, `${base}/media/images/gallery/3.png`, `${base}/media/images/gallery/4.png`, `${base}/media/images/gallery/5.png`]}></Gallery>
    <Schedule></Schedule>
    <Join></Join>
    <Footer></Footer>
</div>