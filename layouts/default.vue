<template>
  <div>
    <header class="shadow-sm bg-white py-3">
      <nav class="container mx-auto p-4 flex justify-between">
        <NuxtLink to="/" class="font-bold text-xl">Nuxt</NuxtLink>
        <ul class="flex gap-4 font-medium text-lg">
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/about">About</NuxtLink></li>
          <li><NuxtLink to="/products" class="btn">Products</NuxtLink></li>
          <li>
            <NuxtLink to="/products/abc">Fake page (products/abc)</NuxtLink>
          </li>
        </ul>
      </nav>
    </header>

    <!--output the page content  -->
    <div class="container mx-auto p-4">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.router-link-exact-active {
  color: #e0144c;
}
</style>
