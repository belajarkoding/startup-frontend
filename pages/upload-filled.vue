<template>
  <div class="container mx-auto h-screen flex justify-center items-center">
    <div class="w-full lg:w-1/3">
      <div class="flex justify-center items-center mx-auto mb-4 w-40">
        <div class="relative">
          <nuxt-link to="/upload-filled">
            <img
              src="/avatar-filled.jpg"
              alt=""
              class="rounded-full border-white border-4"
            />
            <img
              src="/icon-avatar-change.svg"
              alt=""
              class="absolute right-0 bottom-0 pb-2"
            />
          </nuxt-link>
        </div>
      </div>
      <h2 class="font-normal mb-3 text-3xl text-white text-center">
        Hi, Julia
      </h2>
      <p class="text-white text-center font-light">
        Please upload your selfie
      </p>
      <div class="mb-4 mt-6">
        <div class="mb-3">
          <button
            class="block w-full bg-orange-button hover:bg-orange-500 text-white font-semibold px-6 py-4 text-lg rounded-full"
          >
            Sign Up Now
          </button>
        </div>
      </div>
      <div>
        <div class="mb-4">
          <button
            class="block w-full bg-transparent border-white border hover:bg-white hover:bg-opacity-25 text-white font-light px-6 py-4 text-lg rounded-full"
          >
            Skip
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'auth',
}
</script>

<style lang="scss" scoped>
.auth-background {
  background-image: url('/sign-in-background.jpg');
  background-position: center;
  background-size: cover;
}
</style>
