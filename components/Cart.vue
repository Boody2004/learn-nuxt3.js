<template>
  <div class="dropdown relative">
    <IconCart />
    <div
      class="dropdown-menu shadow-md absolute left-0 p-3 opacity-0 pointer-events-none bg-slate-400 rounded-md"
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
const url = "https://fakestoreapi.com/products";
const { data: products } = await useFetch(url);
</script>

<style scoped>
.dropdown-menu {
  top: calc(100% + 0.25rem);
  transform: translateY(-10px);
  transition: opacity 200ms ease-in-out, transform 200ms ease-in-out;
}
.dropdown > .link:focus + .dropdown-menu {
  opacity: 1;
  transform: translateY(0);
  pointer-events: auto;
}
</style>
