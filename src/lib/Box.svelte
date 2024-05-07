<script lang='ts'>
    export let taken: boolean;

    const NOT_TAKEN_COLOR = "#15803d"
    const TAKEN_COLOR = "#b91c1c"

    $: color = taken ? TAKEN_COLOR : NOT_TAKEN_COLOR
</script>

<div class='aspect-[1/2.5] lg:aspect-[1/1.5] border-2 border-black' style:background-color={color}/>