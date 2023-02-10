<script>
	import Nav from "./Nav.svelte";
	import {Router} from "svelte-routing"
	import Contenido from "./Contenido.svelte";
</script>
<h1>Mi aplicación banana</h1>
<Router>
	<Nav/>
	<Contenido/>
</Router>

<style>

:global(body){
		margin: 0%;
		padding: 0%;

	}
	h1{
		text-align: center;
		font-size: 50px;
		font-family: Verdana, Geneva, Tahoma, sans-serif;
	}
	:global(*){
		color: #2d572c;

		background-color:#ffdf00;
	}
	:global(a) {
	color: #de4c8a;
	font-size: 20px;
	font-weight: bold;
	text-decoration: none;
}

:global(a:hover){
	text-decoration: underline;
	color: #2d572c;
}
	
</style>