<script>
	import Home from './pages/Home.svelte'
</script>

<main>
	<Home />
</main>

<svelte:head>
	<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" crossorigin="anonymous">
</svelte:head>

<style>
	@media print {
		* {
   			font-size: 13px;
   			line-height: 1.5;
		}
	}
</style>