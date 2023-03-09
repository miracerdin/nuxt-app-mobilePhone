<template>
  <button
    class="text-white mt-1 ml-1 hover:bg-slate-700 transition-all p-2 rounded-md bg-blue-600"
    @click="moveToAbout"
  >
    Take me to about apge
  </button>
  Hello Index
</template>
<script setup>
function moveToAbout() {
  navigateTo("about");
}
</script>
