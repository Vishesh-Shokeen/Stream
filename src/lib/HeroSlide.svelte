<script>
export let name;
export let src;
</script>

<div>
    <img {src} alt="Featured">
    <button>{name}</button>
</div>


<style>
div{
    display: grid;
    grid-template-areas: 'stack';
    place-items: center;
    scroll-snap-align: start;
}

div > *{
    grid-area: stack;
}
</style>