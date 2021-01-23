<script>
    const title = "FRUIT SHOW";
    const location = "HAMBURG   |   ISTANBUL   |   LONDON";
    const date = "AUGUST  -  24  -  2021";
    const imageText = "Papaya - @crazy_papaya";
    const src = "../assets/bon-vivant-Ooj1c6fhdFM-unsplash.jpg";
    const buttonLabel = "BUY TICKETS";

    function handleClick() {
        alert("🎫");
    }

    let y;
</script>

<style>
    section {
        height: 100vh;
        display: flex;
    }

    h1 {
        color: #e14900;
        font-size: 9em;
        margin: 0;
        letter-spacing: 0.2em;
        font-style: italic;
        font-family: Shrikhand, cursive;
    }

    button {
        margin: 15px;
        background-color: transparent;
        border-color: #253906;
        border-width: medium;
        padding: 15px;
        font-size: larger;
        color: #253906;
        font-weight: bold;
    }

    button:hover {
        animation: shake-bottom 0.8s cubic-bezier(0.455, 0.03, 0.515, 0.955)
            both;
    }

    .title-container p {
        width: 60%;
        line-height: 1.8em;
    }

    .title-container {
        background-color: transparent;
        position: absolute;
        z-index: 1;
        top: 10%;
        bottom: 30%;
        right: 30%;
        left: 30%;
        display: flex;
        align-items: flex-end;
        justify-content: space-evenly;
        flex-direction: column;
    }

    .stage-left {
        width: 40vw;
        height: 100vh;
        background-color: #fda82b;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }
    .stage-right {
        width: 60vw;
        height: 100vh;
        background-color: white;
    }

    .stage-left__image {
        width: 58%;
        height: 60%;
        background-color: #f8c188;
        position: relative;
    }

    .stage-left__image-text {
        position: absolute;
        bottom: -15px;
        right: -25px;
    }

    .stage-left__date {
        position: absolute;
        left: -45px;
        bottom: 100px;
        transform: rotate(-90deg);
    }
    .stage-left__location {
        position: absolute;
        bottom: 30px;
    }

    @keyframes shake-bottom {
        0%,
        100% {
            transform: rotate(0deg);
            transform-origin: 50% 100%;
        }
        10% {
            transform: rotate(2deg);
        }
        20%,
        40%,
        60% {
            transform: rotate(-4deg);
        }
        30%,
        50%,
        70% {
            transform: rotate(4deg);
        }
        80% {
            transform: rotate(-2deg);
        }
        90% {
            transform: rotate(2deg);
        }
    }
</style>

<svelte:window bind:scrollY={y} />

<section style="opacity: {1 - Math.max(0, y / 40)}">
    <div class="title-container">
        <h1>{title}</h1>
        <p>
            Lemon tahini dressing dill chocolate hummus guacamole seeds kung pao
            pepper Malaysian sriracha pecans basmati hearty roasted peanuts
            lychee ginger carrot spiced juice avocado dressing drizzle seasonal.
        </p>
        <button on:click={handleClick}>{buttonLabel}</button>
    </div>
    <div class="stage-left">
        <div class="stage-left__image">
            <p class="stage-left__image-text">{imageText}</p>
        </div>
        <p class="stage-left__date">{date}</p>
        <p class="stage-left__location">{location}</p>
    </div>
    <div class="stage-right" />
</section>
