<template>
  <!-- <HomeWelcome /> -->

  <!-- <button @click="toggle">Toggle</button> -->

  <a @click="view('home')">Home</a>
  <a @click="view('counter')">Counter</a>

  <NuxtPage />

  <LazyHomeWelcome v-if="page === 'home'" />

  <LazyCounter v-if="page === 'counter'" />
  <!-- <home-welcome />  same thing with HomeWelcome -->
  <!-- <Counter /> -->
  <!-- <component :is="MyComponent"> </component> -->
</template>
<script setup>
// const MyComponent = ref(resolveComponent("Counter"));

// const MyComponent = ref("counter");

// function toggle() {
//   MyComponent.value = "welcome";
// }

const page = ref("home");

function view(name) {
  page.value = name;
}
</script>
