<script>
    import HeroSlide from "./HeroSlide.svelte";
    import poster from "/slide2.jpg";
</script>

<section>
    <HeroSlide src={poster} name="Ghibli" />
    <HeroSlide src={poster} name="Ghibli" />
    <HeroSlide src={poster} name="Ghibli" />
    <HeroSlide src={poster} name="Ghibli" />
    <HeroSlide src={poster} name="Ghibli" />
</section>

<style>
    section {
        display: grid;
        grid-auto-flow: column;
        overflow: scroll;
        overflow-y: hidden;
        grid-auto-columns: 100vw;
        gap: 1rem;

        scroll-snap-type: inline mandatory;
    }
</style>
