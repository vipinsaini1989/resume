<script>
import { prop_dev } from 'svelte/internal';

    import Template1 from '../components/Template1.svelte';
    import Header from '../components/header.svelte';
	import pf from '../portfolio.json';
</script>

<main>
    <Header />
    <Template1 data={pf} />
</main>

<svelte:head>
    <title>{pf.personal.name} Portfolio</title>
</svelte:head>