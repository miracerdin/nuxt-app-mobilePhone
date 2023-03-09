<template>
  <div>
    <Head>
      <Title>Nuxt 3 - iphone{{ name }}</Title>
    </Head>
    <div class="flex justify-center w-full mt-20">
      <div class="grid grid-cols-2">
        <div>
          <img :src="`/images/iphone-13-pink-select-2021.png`" alt="" />
        </div>
        <div>
          <h1 class="text-3xl">Iphone {{ name }}</h1>
          <button
            @click="addToCart"
            class="p-3 bg-indigo-900 text-white rounded-md mt-5 w-48"
          >
            <span v-if="!inCart()">Buy now</span>
            <span v-else>Remove from cart</span>
          </button>
        </div>
      </div>
    </div>
  </div>
  <!-- <div>Iphone {{ name }}</div> -->
</template>

<script setup>
const route = useRoute();

const name = computed(() => {
  return route.params.name.replaceAll("-", " ");
});

const fullName = computed(() => {
  return `iphone-${route.params.name}`;
});

function inCart() {
  return !!cart.value.find((ct) => ct.name === fullName.value);
}

const cart = useCart();
function addToCart() {
  if (!inCart()) {
    cart.value.push({
      name: fullName,
    });
  } else {
    cart.value = cart.value.filter((ct) => ct.name !== fullName.value);
  }
}

// useHead({
//   title: `Nuxt3 - ${route.params.name}`,
// });
</script>
