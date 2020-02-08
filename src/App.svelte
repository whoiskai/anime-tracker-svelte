<script>
	import { Router, Route } from "svelte-routing";
	import NavLink from "./components/NavLink.svelte";
	import About from "./routes/About.svelte"
	import Home from "./routes/Home.svelte"
	export let url = "";
</script>

<Router url="{url}">
	<nav>
		<NavLink to="/">Home</NavLink>
		<NavLink to="about">About</NavLink>
	</nav>
	<div>
		<Route path="about" component="{About}" />
		<Route path="/" component="{Home}" />
	</div>
</Router>
