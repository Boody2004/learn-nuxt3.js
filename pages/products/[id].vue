<template>
  <div>
    <p>Product details for {{ id }}</p>
    <p>
      LoremDolor do proident laboris ullamco magna amet ad reprehenderit fugiat
      consectetur dolore fugiat mollit. Cillum in id eiusmod pariatur consequat
      anim.
    </p>
  </div>
</template>

<script setup>
const { id } = useRoute().params;

definePageMeta({
  layout: "products",
});
</script>

<style scoped></style>
