<template>
  <header class="flex items-center">
    <div style="height: 54px" class="pr-5">
      <img src="/logo.svg" alt="logo" class="h-full" />
    </div>
    <ul class="flex items-center">
      <li>
        <nuxt-link
          class="text-white hover:text-teal-500 text-lg px-4 py-3"
          to="/"
        >
          Home
        </nuxt-link>
      </li>
      <li>
        <a class="text-white hover:text-teal-500 text-lg px-4 py-3" href="#"
          >Project</a
        >
      </li>
      <li>
        <a class="text-white hover:text-teal-500 text-lg px-4 py-3" href="#"
          >Features</a
        >
      </li>
      <li>
        <a class="text-white hover:text-teal-500 text-lg px-4 py-3" href="#"
          >Success Stories</a
        >
      </li>
    </ul>
    <ul class="flex ml-auto items-center mt-2">
      <li>
        <nuxt-link
          to="/register"
          class="inline-block bg-transparent border-white border hover:bg-white hover:bg-opacity-25 text-white font-light w-40 text-center px-6 py-1 text-lg rounded-full mr-4"
        >
          Sign Up
        </nuxt-link>
      </li>
      <li>
        <nuxt-link
          to="/login"
          class="inline-block bg-transparent border-white border hover:bg-white hover:bg-opacity-25 text-white font-light w-40 text-center px-6 py-1 text-lg rounded-full"
        >
          My Account
        </nuxt-link>
      </li>
    </ul>
  </header>
</template>
