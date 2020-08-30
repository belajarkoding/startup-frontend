<template>
  <div class="container mx-auto mt-5">
    <div>
      <h1 class="title text-lg">Homepage</h1>
      <ul class="list-disc">
        <li>
          <nuxt-link to="/login">Login</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/register">Register</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/register-success">Register (Success)</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/upload">Upload</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/upload-filled">Upload (Filled)</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/fund-success">Fund (Success)</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/404">404 Page</nuxt-link>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {}
</script>
