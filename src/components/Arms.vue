<script setup>
    
</script>

<template>
    <div><img class="rotating" src="/mcgregor_crest_coat_of_arms.png" alt="Coat of Arms"></div>
</template>

<style scoped>
    @keyframes rotate {
        0% {
            transform: rotateX(0deg);
        }
        50% {
            transform: rotate(360deg);
        }
        100% {
            transform: rotateX(360deg)
        }
    }
    img.rotating {
        animation: rotate 15s infinite ease-in-out;
        transform-style: preserve-3d;
    }

</style>