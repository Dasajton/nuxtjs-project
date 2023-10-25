<template>
  <div>
    <nav
      class="bg-blue-600 shadow-lg p-3 text-white text-lg flex justify-between gap-10"
    >
      <div class="flex gap-4">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/iphone">iPhones</NuxtLink>
        <p>Cart ( {{ cart.length }} )</p>
        <p>Total Route Changed: {{ pageVisitCount }}</p>
      </div>

      <div v-if="auth.isAuthenticated">
        <NuxtLink to="/profile">Profile</NuxtLink>
        <button class="ml-8" @click="logout">Logout</button>
      </div>

      <NuxtLink v-else to="/login">Login</NuxtLink>
    </nav>
  </div>
</template>

<script setup>
const cart = useCart();
const auth = useAuth();
const pageVisitCount = usePageVisitCount();

function logout() {
  auth.value.isAuthenticated = false;
}
</script>
