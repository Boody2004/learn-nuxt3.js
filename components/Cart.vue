<template>
  <div class="dropdown relative">
    <IconCart @click="isOpen = !isOpen" />

    <div
      v-show="isOpen"
      class="dropdown-menu shadow-md absolute left-0 p-3 bg-slate-400 rounded-md"
    >
      <div class="max-h-80 overflow-y-scroll">
        <div v-for="product in products">
          <div class="my-3 mr-3 p-4 rounded-md shadow-md bg-white">
            <div class="flex items-center justify-between">
              <img :src="product.image" alt="img" class="h-20" />
              <h1 class="font-bold">EGP {{ product.price }}</h1>
            </div>
            <h1 class="text-center mt-4 font-medium max-w-[15rem]">
              {{ product.title }}
            </h1>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data: products } = await useFetch("https://fakestoreapi.com/products");
</script>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
};
</script>

<style scoped>
.dropdown-menu {
  top: calc(100% + 0.7rem);
  transform: translateY(-10px);
  transition: opacity 200ms ease-in-out, transform 200ms ease-in-out;
}
</style>
