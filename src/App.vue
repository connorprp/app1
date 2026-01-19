<script setup>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'
import GreyBox from '@/components/GreyBox.vue';
import FancyButton from './components/FancyButton.vue';
import Arms from "./components/Arms.vue"


let text = ref('SIGMA');
let rainbowActive = ref(false)

function changeText() {
  if(text.value == "SIGMA") {
    text.value = "ALPHA"
  } else {
    text.value = "SIGMA"
  }
}

function activateRainbow() {
  rainbowActive.value = !rainbowActive.value;
}

</script>

<template>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Exile&display=swap" rel="stylesheet">

  <div id="grid">
    <div class="item">
      <GreyBox>
        {{ text }}
      </GreyBox>
    </div>
    <div class="item">
      <GreyBox class="curve" />
    </div>
    <div class="item">
      <GreyBox><Arms /></GreyBox>
    </div>
    <div class="item">
      <GreyBox>
        <FancyButton :rainbowActive="rainbowActive" class="top" @top-clicked="changeText" buttonType="top">A</FancyButton>
        <FancyButton :rainbowActive="rainbowActive" class="bottom" @bottom-clicked="activateRainbow" buttonType="bottom">B</FancyButton>
      </GreyBox>
    </div>
  </div>
</template>

<style scoped>
#grid {
  margin: 10px;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: 1fr 1fr;
  height: calc(100vh - 20px);
  gap: 10px;
}

.item {
  font-family: 'Exile';
  font-size: 64px;
}

#curve.item {
  border-top-right-radius: 100%;
}
</style>
