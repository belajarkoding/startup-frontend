<template>
  <div class="landing-page">
    <section class="landing-hero pt-5">
      <div class="header__bg"></div>
      <div class="container mx-auto relative">
        <header class="flex items-center">
          <div style="height: 54px;" class="pr-5">
            <img src="/logo.svg" alt="logo" class="h-full" />
          </div>
          <ul class="flex items-center">
            <li>
              <a
                class="text-white hover:text-teal-500 text-lg px-4 py-3"
                href="/"
                >Home</a
              >
            </li>
            <li>
              <a
                class="text-white hover:text-teal-500 text-lg px-4 py-3"
                href="/pricing"
                >Project</a
              >
            </li>
            <li>
              <a
                class="text-white hover:text-teal-500 text-lg px-4 py-3"
                href="/features"
                >Features</a
              >
            </li>
            <li>
              <a
                class="text-white hover:text-teal-500 text-lg px-4 py-3"
                href="/story"
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
        <div class="flex items-center pt-10 px-5 md:px-0">
          <div class="w-1/2">
            <h1 class="text-4xl text-white mb-5">
              We helps <u class="hero-underline">startup</u> to <br />
              getting started & <u class="hero-underline">funding</u> <br />
              their truly needs
            </h1>
            <p class="text-white text-xl font-light mb-8">
              Fund the best idea to become <br />
              a real product and be the contributor
            </p>
            <button
              @click="$router.push({ path: '/' })"
              class="block bg-orange-button hover:bg-green-button text-white font-semibold px-12 py-3 text-xl rounded-full"
            >
              Find a Project
            </button>
          </div>
          <div class="w-1/2 flex justify-center">
            <img src="/hero-image@2x.png" alt="crowdfunding project" />
          </div>
        </div>
      </div>
    </section>
    <section class="container mx-auto pt-24">
      <div class="flex justify-between items-center">
        <div class="w-auto">
          <h2 class="text-3xl text-gray-900 mb-12">
            New projects you can <br />
            taken care of
          </h2>
        </div>
        <div class="w-auto mt-10">
          <a class="text-gray-900 hover:underline text-sm" href="">View All</a>
        </div>
      </div>
      <div class="flex justify-start items-center mt-3">
        <div class="w-1/3 p-6 border border-gray-500 rounded-20">
          <div class="item">
            <figure class="item-image">
              <img
                src="https://media.bwamicro.com/images/1593528041154.jpg"
                alt="Graphic Designer 01"
                class="rounded-20"
              />
            </figure>
            <div class="item-meta">
              <h4 class="text-3xl text-gray-900 mt-5">Robotic Hand</h4>
              <p class="text-md font-light text-gray-900">
                Creating robotic hand for better movement
              </p>
            </div>
            <a class="link-wrapped" href="/courses/1"></a>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.landing-hero {
}
.header__bg {
  position: absolute;
  top: 0;
  bottom: 0;
  right: 0;
  left: 0;
  width: 100%;
  height: 640px;
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-color: #3b41e3;
  transform: skewY(-6deg);
  transform-origin: top left;
}

.hero-underline {
  text-decoration-color: #1abc9c;
}
</style>
