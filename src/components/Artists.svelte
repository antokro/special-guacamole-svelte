<script>
    import { fade } from "svelte/transition";
    const carouselPhotos = [
        "#94AC24",
        "#DF5919",
        "#A0B249",
        "#CC8360",
        "#AAB47D",
        "#CDAD9D",
        "#C0C4AC",
    ];
    let currentCarouselIndex = 0;

    function handleRightClick() {
        currentCarouselIndex =
            (currentCarouselIndex + 1) % carouselPhotos.length;
        console.log(currentCarouselIndex);
    }

    function handleLeftClick() {
        currentCarouselIndex =
            (currentCarouselIndex - 1) % carouselPhotos.length;
        console.log(currentCarouselIndex);
    }
</script>

<style>
    section {
        height: 100vh;
        position: relative;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .carousel-image {
        height: 600px;
        width: 900px;
        position: absolute;
    }
    button {
        position: absolute;
    }

    .button-right {
        right: 15px;
    }
    .button-left {
        left: 15px;
    }
</style>

<section id="artists">
    <button class="button-left" on:click={handleLeftClick}>&larr;</button>
    <button class="button-right" on:click={handleRightClick}>&rarr;</button>
    {#each [carouselPhotos[currentCarouselIndex]] as photo (currentCarouselIndex)}
        <div
            transition:fade={{ duration: 500 }}
            class="carousel-image"
            style="background-color:{photo}" />
    {/each}
</section>
