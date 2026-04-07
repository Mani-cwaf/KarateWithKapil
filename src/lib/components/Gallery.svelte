<script>
	import '../../app.css';
    let { images } = $props()
</script>

<div class="gallery" id="gallery">
	<h2>GALLERY</h2>

	<div class="container">
		{#each images as image}
			<div>
				<img src={image} alt="">
				<div class="caption">
					<p>caption</p>
				</div>
			</div>
		{/each}
	</div>
</div>

<style>
	.gallery {
		padding: 2rem;
		background: var(--black) radial-gradient(circle, rgba(50,50,50,0.3) 1px, transparent 1px);
 		background-size: 20px 20px;
  		background-attachment: fixed;;
		background-position: center;
	}

	h2 {
        font-family: 'Cormorant', serif;

		font-size: 1.5rem;
		margin-bottom: 1rem;
		letter-spacing: 2px;
		color: var(--light-grey);
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
</style>