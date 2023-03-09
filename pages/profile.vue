<template>Hello from profile</template>
<script>
definePageMeta({
  layout: "sidebar",

  // middleware: () => {
  //   const auth = useAuth();
  //   return auth.value.isAuthenticated;
  // },

  middleware: ["auth"],
});
</script>
