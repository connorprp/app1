<script setup>
import { ref } from 'vue';
let emit = defineEmits(['top-clicked', 'bottom-clicked']);
let clicked = ref(false);
let props = defineProps({
    rainbowActive: Boolean
})

function handleClick(buttonType) {
    if (buttonType === 'top') {
        emit('top-clicked');
    } else if (buttonType === 'bottom') {
        emit("bottom-clicked")
    }
}
</script>

<template>
    <div class="button-container"><button :class="{ rainbowActive: props.rainbowActive }"
            @click="handleClick($attrs.buttonType)">
            <slot></slot>
        </button></div>
</template>

<style scoped>
.button-container {
    position: relative;
}

button {
    position: absolute;
    left: -50px;
    border: none;
    color: #fff;
    font-size: 20px;
    cursor: pointer;
    background: #dc143c;
    transition: box-shadow .15s ease, transform .15s ease;
    width: 100px;
    height: 100px;
}

.top button {
    clip-path: polygon(50% 0%, 100% 100%, 0% 100%);
    bottom: 0px;
}

.bottom button {
    clip-path: polygon(0% 0%, 100% 0%, 50% 100%);
    top: 0px;
}

button:active {
    transform: scale(0.95);
    filter: drop-shadow(0 5px 10px rgba(0, 0, 0, 0.8));
}

@keyframes rainbow {
    0% {
        filter: hue-rotate(0deg);
    }

    100% {
        filter: hue-rotate(360deg)
    }
}

button.rainbowActive {
    animation: rainbow 3s ease-in-out infinite alternate;
}
</style>