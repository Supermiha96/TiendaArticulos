<script>
    import { onMount } from "svelte";
    import Buscar from "./buscar.svelte";
    let data = [];
    let datosFiltrados =[];
    let patron = '';
    

    let getArticulos = async () => {
        const response = await fetch(
            "https://tiendabackend.fly.dev/api/articulos/"
        );
        data = await response.json();
    };

    onMount(getArticulos);
    $:datosFiltrados = data.filter(articulo=> RegExp(patron , "i").test(articulo.nombre) );
</script>

<h1>Articulos</h1>
<Buscar bind:busqueda = {patron}/>
<hr/>
<ul>
    {#each datosFiltrados as item}
        <li>{item.nombre} ->{item.precio}$</li>
    {/each}
</ul>

<style>
    h1{
        margin: 50px;
    }
</style>