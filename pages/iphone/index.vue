<template>
  <div class="grid grid-cols-4 gap-4 p-5">
    <nuxt-link
      v-for="iphone in iphones"
      :key="iphone"
      :to="`/iphone/${iphone}`"
      class="shadow-lg border rounded-lg text-center"
    >
      <h1>{{ iphone }}</h1>
      <div class="flex justify-center">
        <img width="200" :src="`/images/${iphone}.jpg`" alt="" />
      </div>
    </nuxt-link>
  </div>
</template>

<script setup>
useHead({
  title: "Nuxt3 - iPhones",
});

const iphones = ["iphone-12", "iphone-12-pro", "iphone-13", "iphone-13-pro"];

// const { data } = useFetch("/api/iphones");
// const iphones = data.value;
</script>
