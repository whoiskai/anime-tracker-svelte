<script>
	import { Router, Route, link } from "svelte-routing";
	import Link from "./components/NavLink.svelte";
	import About from "./routes/About.svelte"
	import Home from "./routes/Home.svelte"

	export let url = "";

	function getProps({ location, href, isPartiallyCurrent, isCurrent }) {
		console.log(location)
		console.log(href)
		console.log(isPartiallyCurrent)
		console.log(isCurrent)
		const isActive = href === "/" ? isCurrent : isPartiallyCurrent || isCurrent;

		if (isActive) {
			return { class: "active" };
		}
		return {};
	}
</script>

<svelte:head>
	<!-- Import Bootstrap 4 CDN -->
	<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css">
	<script src="https://code.jquery.com/jquery-3.4.1.slim.min.js" integrity="sha384-J6qa4849blE2+poT4WnyKhv5vZF5SrPo0iEjwBvKU7imGFAV0wwj1yYfoRSJoZ+n" crossorigin="anonymous"></script>
	<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js" integrity="sha384-Q6E9RHvbIyZFJoft+2mJbHaEWldlvI9IOYy5n3zV9zzTtmI3UksdQRVvoxMfooAo" crossorigin="anonymous"></script>
	<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js" integrity="sha384-wfSDF2E50Y2D1uUdj0O3uMBJnjuUD4Ih7YwaYd1iqfktj0Uod8GCExl3Og8ifwB6" crossorigin="anonymous"></script>
</svelte:head>


<Router url="{url}">
	<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
		<a class="navbar-brand" href="#">Anime Tracker</a>
		<button class="navbar-toggler" type="button" data-toggle="collapse" data-target=".navbar-collapse" aria-controls=".navbar-collapse" aria-expanded="false" aria-label="Toggle navigation">
			<span class="navbar-toggler-icon"></span>
		</button>
		<div class="collapse navbar-collapse" id="navbarNav">
			<ul class="navbar-nav">
				<li class="nav-item">
					<Link to="/" class="active">Home</Link>
				</li>
				<li class="nav-item">
					<Link to="about">About</Link>
				</li>
			</ul>
		</div>
	</nav>
	<div class="container-fluid">
		<Route path="about" component="{About}" />
		<Route path="/" component="{Home}" />
	</div>
</Router>

<style>
</style>