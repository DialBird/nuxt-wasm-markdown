<script lang="ts" setup></script>

<template>
  <div class="h-screen flex flex-col">
    <div class="navbar bg-blue-500">
      <div class="flex-1">
        <NuxtLink to="/" class="btn btn-ghost normal-case text-xl text-white font-mono font-[300]"
          >Nuxt x Rust Markdown</NuxtLink
        >
        <!--    <a class="btn btn-ghost normal-case text-xl text-white font-roboto font-[400]">Nuxt x Rust Markdown</a>-->
        <!--    <a class="btn btn-ghost normal-case text-xl text-white font-sans font-[400]">Nuxt x Rust Markdown</a>-->
        <!--    <a class="btn btn-ghost normal-case text-xl text-white font-open-sans font-[400]">Nuxt x Rust Markdown</a>-->
      </div>
      <div class="flex-none">
        <ul class="menu menu-horizontal p-0">
          <li>
            <NuxtLink to="/about" class="text-white font-mono">About</NuxtLink>
          </li>
        </ul>
      </div>
    </div>
    <div class="container mx-auto flex-1 pt-4 pb-12">
      <slot />
    </div>
  </div>
</template>
