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
    $: currentCarouselIndex = 0;

    function handleRightClick() {
        currentCarouselIndex =
            (currentCarouselIndex + 1) % carouselPhotos.length;
    }

    function handleLeftClick() {
        currentCarouselIndex =
            (currentCarouselIndex - 1) % carouselPhotos.length;
    }

    function setCarouselIndex(index) {
        currentCarouselIndex = index;
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
        margin: 15px;
        background-color: transparent;
        border-color: #253906;
        border-width: medium;
        padding: 15px;
        font-size: larger;
        color: #253906;
        font-weight: bold;
    }

    .button-right {
        right: 100px;
    }
    .button-left {
        left: 100px;
    }

    .slider-index {
        width: 20px;
        height: 20px;
        margin: 10px;
        border-radius: 50%;
        background-color: #253906;
        opacity: 0.5;
    }

    .slider-index.active {
        opacity: 1;
    }

    .slider-index-container {
        position: absolute;
        bottom: 100px;
        margin: auto;
        display: flex;
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
    <div class="slider-index-container">
        <div
            class={currentCarouselIndex === 1 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(1)} />
        <div
            class={currentCarouselIndex === 2 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(2)} />
        <div
            class={currentCarouselIndex === 3 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(3)} />
        <div
            class={currentCarouselIndex === 4 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(4)} />
        <div
            class={currentCarouselIndex === 5 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(5)} />
        <div
            class={currentCarouselIndex === 6 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(6)} />
        <div
            class={currentCarouselIndex === 7 ? 'slider-index active' : 'slider-index'}
            on:click={() => setCarouselIndex(7)} />
    </div>
</section>
