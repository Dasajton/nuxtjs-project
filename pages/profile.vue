<template>
  <p>Welcome David</p>
</template>

<script>
definePageMeta({
  layout: "sidebar",
  middleware: ["auth"],
});
</script>
