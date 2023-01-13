<template>
  <section>
    <header class="shadow-md bg-white">
      <div class="container mx-auto p-4">
        <div class="dropdown relative">
          <button class="link flex">
            <span class="px-2 rounded-full bg-red-500 text-white">1</span>
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-8 h-8"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 00-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 00-16.536-1.84M7.5 14.25L5.106 5.272M6 20.25a.75.75 0 11-1.5 0 .75.75 0 011.5 0zm12.75 0a.75.75 0 11-1.5 0 .75.75 0 011.5 0z"
              />
            </svg>
          </button>
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
      </div>
    </header>

    <main class="container mx-auto p-4">
      <h2 class="font-medium text-center text-4xl">Cart</h2>
    </main>
  </section>
</template>

<script setup>
const url = "https://fakestoreapi.com/products?limit=18";
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
