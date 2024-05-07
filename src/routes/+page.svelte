<script lang='ts'>
    import { onMount } from "svelte";
    import Box from "../lib/Box.svelte";
    import "../app.pcss";

    const url = 'http://65.108.223.40:8080'
    $: data = [false, false, false, false, false, false]

    onMount(() => {
        async function fetchData() {
            const res = await fetch(url)
            data = await res.json()
        }

        const interval = setInterval(fetchData, 5000)

        return () => clearInterval(interval)
    })
</script>

<div class='h-screen w-screen grid grid-cols-6 place-content-center'>
    {#each {length: 6} as _, i }
        <Box taken={data[i]}/>
    {/each}
    {data}
</div>