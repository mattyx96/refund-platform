<template>
    <div class="overflow-hidden">
        <div class="gradient-1"></div>
        <div class="gradient-2"></div>
<!--        <div class="gradient-3"></div>-->
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: "BlurBackground"
}
</script>

<style scoped>
.gradient-1 {
    position: absolute;
    height: 100%;
    width: 100%;
    z-index: -100;
    background: url("../../assets/bkg.png");
}

.gradient-2 {
}

/* if backdrop support: very transparent and blurred */
@supports ((-webkit-backdrop-filter: none) or (backdrop-filter: none)) {
    .gradient-1 {
        width: 75%;
        height: 120%;
        right: -15%;
        bottom: -35%;
        background: conic-gradient(from 192deg at 44.77% 38%, #FA8792 -54.94deg, #561BBE 28.29deg, #70E6FB 157.82deg, #FBF8B3 220.83deg, #FA8792 305.06deg, #561BBE 388.29deg);
        transform: matrix(1, 0, 0, -1, 0, 0);
        filter: blur(10rem);
    }
}

@media (max-width:480px)  {
    .gradient-1 {
        position: absolute;
        width: 100%;
        height: 140%;
        right: -20%;
        bottom: -80%;
        /*clip-path: polygon(100% 81%, 60% 60%, 25% 100%, 6% 67%, 39% 0, 100% 36%);

        -moz-box-shadow:30rem 30rem 30rem #000000;
        -webkit-box-shadow:30rem 30rem 30rem #000000;
        box-shadow:30rem 30rem 30rem #000000;
        -webkit-border-radius: 30rem;
        -moz-border-radius: 30rem;
        border-radius: 30rem;*/

        background: conic-gradient(from 192deg at 44.77% 38%, #FA8792 -54.94deg, #561BBE 28.29deg, #70E6FB 157.82deg, #FBF8B3 220.83deg, #FA8792 305.06deg, #561BBE 388.29deg);
        filter: blur(10rem);
        transform: matrix(1, 0, 0, -1, 0, 0);
    }

    .gradient-2 {
        /* Vector 104 */

        position: absolute;
        width: 75%;
        height: 120%;
        left: -35%;
        top: -55%;

        box-shadow: 0 0 15px 10px #141414;

        /*clip-path: polygon(100% 81%, 60% 60%, 25% 100%, 6% 67%, 39% 0, 100% 36%);*/

        background: conic-gradient(from 192deg at 44.77% 38%, #FA8792 -54.94deg, #561BBE 28.29deg, #70E6FB 157.82deg, #FBF8B3 220.83deg, #FA8792 305.06deg, #561BBE 388.29deg);
        filter: blur(5rem);
        transform: matrix(1, 0, 0, -1, 0, 0);
        z-index: -1;
    }
}
</style>
