<template>
  <div>
    <div class="container flex p-4 mx-auto md:px-10 justify-between">
      <div class="flex">
        <div class="w-6">
          <img src="../assets/coding.svg" alt="">
        </div>
        <div class="ml-2 flex flex-col">
          <p class="font-medium tracking-tight md:tracking-normal text-sm">
            Pusat Informasi dan Koordinasi
          </p>
          <p class="text-xs font-medium">
            Covid 19
          </p>
        </div>
      </div>
      <div class="flex items-center font-medium text-sm">
        <div class="hidden lg:flex flex-row">
          <nuxt-link to="/" class="mx-4 hover:bg-teal-200 p-2 rounded">
            Home
          </nuxt-link>
          <nuxt-link to="/data" class="mx-4 hover:bg-teal-200 p-2 rounded">
            Data
          </nuxt-link>
          <nuxt-link to="/berita" class="mx-4 hover:bg-teal-200 p-2 rounded">
            Berita
          </nuxt-link>
          <nuxt-link to="/kontak" class="mx-4 hover:bg-teal-200 p-2 rounded">
            Kontak
          </nuxt-link>
        </div>
        <div class="hidden md:block">
          <button class="bg-teal-500 p-2 rounded text-white hover:bg-teal-700 font-medium">
            Download App
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
