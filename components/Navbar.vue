<template>
  <nav class="bg-purple-900 shadow p-3 justify-between text-white text-lg flex">
    <div class="flex">
      <NuxtLink class="mr-4" to="/">Home </NuxtLink>
      <NuxtLink class="mr-4" to="/iphone"> İphone</NuxtLink>
      <p class="mr-4">Cart({{ cart.length }})</p>
      <p>Total route change: {{ pageVisitCount }}</p>
    </div>

    <div v-if="auth.isAuthenticated">
      <NuxtLink to="/profile">Profile</NuxtLink>
      <button class="ml-4" @click="logout">Logout</button>
    </div>

    <NuxtLink v-else to="/login">Login</NuxtLink>
  </nav>
</template>

<script setup>
const cart = useCart();
const auth = useAuth();
const pageVisitCount = usePageVisitCount();

function logout() {
  auth.value.isAuthenticated = false;
}
</script>
