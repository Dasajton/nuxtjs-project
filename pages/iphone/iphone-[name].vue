<template>
  <div>
    <head>
      <Title>Nuxt3 - iPhone {{ name }}</Title>
    </head>

    <div class="flex justify-center w-full mt-20">
      <div class="grid grid-cols-2">
        <div>
          <img width="400" :src="`/images/iphone-${route.params.name}.jpg`" />
        </div>
        <div class="text-center">
          <h1 class="text-3xl">iPhone {{ name }}</h1>
          <button
            @click="addToCart"
            class="p-3 bg-blue-800 text-white rounded-md mt-5 w-48"
          >
            <span v-if="isInCart()">Remove from Cart</span>
            <span v-else>Buy Now</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
// Function for replacing all "-" with a " "
const route = useRoute();
const name = computed(() => {
  return route.params.name.replaceAll("-", " ");
});

const fullName = computed(() => {
  return `iphone-${route.params.name}`;
});

// Function for adding an item to the cart

const cart = useCart();

function isInCart() {
  return !!cart.value.find((ct) => ct.name === fullName.value);
}

function addToCart() {
  if (!isInCart()) {
    cart.value.push({ name: fullName });
  } else {
    cart.value = cart.value.filter((ct) => ct.name !== fullName.value);
  }
}

// useHead({
//   title: `Nuxt3 - iPhone ${route.params.name}`,
// });
</script>
