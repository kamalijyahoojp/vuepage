<script setup lang="ts">
import { ref } from 'vue';
import HelloWorld from './components/HelloWorld.vue';
import TheWelcome from './components/TheWelcome.vue';

const product = ref(true);

function switchMypage(sw: boolean) {
  product.value = sw;
}
</script>

<template>
  <header v-if="product">
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="KamaliJ's Open Productions" />
    </div>
  </header>

  <main>
    <TheWelcome @mypage="switchMypage(false);" />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
