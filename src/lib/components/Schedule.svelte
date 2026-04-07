<script>
	import '../../app.css';
</script>

<div class="schedule" id="classes">
	<h1 class="title">SCHEDULE</h1>

	<div class="container">
		<div class="timings">
				<h1 class="days">MONDAY</h1>
				<h1 class="timing">5:30 PM - 6:30 PM</h1>
				<h1 class="type">ALL LEVELS</h1>

				<h1 class="days">WEDNESDAY</h1>
				<h1 class="timing">5:30 PM - 6:30 PM</h1>
				<h1 class="type">ADVANCED</h1>
				
				<h1 class="days">FRIDAY</h1>
				<h1 class="timing">5:30 PM - 6:30 PM</h1>
				<h1 class="type">ALL LEVELS</h1>

				<h1 class="days">SUNDAY</h1>
				<h1 class="timing">9:30 AM - 10:30 AM</h1>
				<h1 class="type">SPARRING <br> PRACTICE</h1>
				
		</div>
		<div class="quote">
			<h2>"The ultimate aim of karate <br> lies not in victory nor defeat, <br> but in the perfection of character."</h2>
			<h3>— GICHIN FUNAKOSHI</h3>
		</div>
	</div>
</div>

<style>
	.schedule {
		font-family: serif;
		padding: 2rem;
		background-size: cover;
		background-position: center;
	}

	.title {
		margin-bottom: 1.5rem;
		font-size: 2.5rem;
	}

	.container {
		display: flex;
		flex-direction: row;
	}

	.days {
		color: var(--light-grey);
		grid-column: 1;
	}

	.timing {
		grid-column: 2;
	}

	.type {
		color: var(--gold);
		grid-column: 3;
	}

	.timings {
		width: 50%;
		padding: 2rem;
		border-right: 1.5px solid var(--gold);
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-template-rows: repeat(4, 1fr);
        font-size: clamp(0.5rem, 0.25rem + 1.5vw, 1.1rem);
	}

	h1 {
		text-align: center;
		line-height: 2;
	}

	.quote {
		width: 50%;
        font-family: 'Cormorant', serif;
		align-self: center;
		justify-content: center;
		text-align: center;
	}

	.quote * {
        font-size: clamp(0.25rem, 0.5rem + 2.5vw, 2rem);
	}

    @media (max-width: 1024px) {
		.container {
			flex-direction: column;
		}

		.timings {
			border: none;
			width: 100%;
		}

		.quote {
			width: 100%;
		}
    }

</style>