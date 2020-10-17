<template>
  <div class="project-page">
    <section class="dashboard-header pt-5">
      <div class="container mx-auto relative">
        <header class="flex items-center">
          <div style="height: 54px" class="pr-5">
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
      </div>
    </section>
    <section class="container mx-auto pt-8">
      <div class="flex justify-between items-center">
        <div class="w-full mr-6">
          <h2 class="text-4xl text-gray-900 mb-2 font-medium">Dashboard</h2>
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="w-3/4 mr-6">
          <h3 class="text-2xl text-gray-900 mb-4">Campaign Details</h3>
        </div>
        <div class="w-1/4 text-right">
          <nuxt-link
            to="/dashboard/projects/create"
            class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-1 rounded inline-flex items-center"
          >
            Edit
          </nuxt-link>
        </div>
      </div>
      <div class="block mb-2">
        <div class="w-full lg:max-w-full lg:flex mb-4">
          <div
            class="border border-gray-400 bg-white rounded p-8 flex flex-col justify-between leading-normal"
          >
            <div>
              <div class="text-gray-900 font-bold text-xl mb-2">
                Cari Uang Buat Gunpla
              </div>
              <p class="text-sm font-bold flex items-center mb-1">
                Description
              </p>
              <p class="text-gray-700 text-base">
                Designed to fit your dedicated typing experience. No matter what
                you like, linear, clicky or a little in between, we’ve got you
                covered with three Gateron switches options (Blue, Brown, Red).
                With a lifespan of 50 million keystroke lifespan we want to make
                sure that you experience same feedback for every keystroke.
              </p>
              <p class="text-gray-700 text-base">
                With N-key rollover (NKRO on wired mode only) you can register
                as many keys as you can press at once without missing out
                characters. It allows to use all the same media keys as
                conventional macOS.
              </p>
              <p class="text-sm font-bold flex items-center mb-1 mt-4">
                What Will Funders Get
              </p>
              <ul class="list-disc ml-5">
                <li>Equity of the startup directly from the founder</li>
                <li>Special service or product that startup has</li>
                <li>
                  You can also sell your equity once the startup going IPO
                </li>
              </ul>
              <p class="text-sm font-bold flex items-center mb-1 mt-4">Price</p>
              <p class="text-4xl text-gray-700 text-base">200.000</p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="w-3/4 mr-6">
          <h3 class="text-2xl text-gray-900 mb-4 mt-5">Gallery</h3>
        </div>
        <div class="w-1/4 text-right">
          <a
            href="#"
            class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-1 rounded inline-flex items-center"
          >
            Upload
          </a>
        </div>
      </div>
      <div class="flex -mx-2">
        <div
          class="relative w-1/4 bg-white m-2 p-2 border border-gray-400 rounded"
        >
          <figure class="item-thumbnail">
            <img src="/project-slider-1.jpg" alt="" class="rounded w-full" />
          </figure>
        </div>
        <div
          class="relative w-1/4 bg-white m-2 p-2 border border-gray-400 rounded"
        >
          <figure class="item-thumbnail">
            <img src="/project-slider-2.jpg" alt="" class="rounded w-full" />
          </figure>
        </div>
        <div
          class="relative w-1/4 bg-white m-2 p-2 border border-gray-400 rounded"
        >
          <figure class="item-thumbnail">
            <img src="/project-slider-3.jpg" alt="" class="rounded w-full" />
          </figure>
        </div>
        <div
          class="relative w-1/4 bg-white m-2 p-2 border border-gray-400 rounded"
        >
          <figure class="item-thumbnail">
            <img src="/project-slider-4.jpg" alt="" class="rounded w-full" />
          </figure>
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="w-3/4 mr-6">
          <h3 class="text-2xl text-gray-900 mb-4 mt-5">Transaction History</h3>
        </div>
      </div>
      <div class="block mb-2">
        <div class="w-full lg:max-w-full lg:flex mb-4" v-for="i in 5" :key="i">
          <div
            class="w-full border border-gray-400 lg:border-gray-400 bg-white rounded p-8 flex flex-col justify-between leading-normal"
          >
            <div>
              <div class="text-gray-900 font-bold text-xl mb-1">
                Galih Pratama
              </div>
              <p class="text-sm text-gray-600 flex items-center mb-2">
                Rp. 200.000 &middot; 12 September 2020
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="cta-clip -mt-20"></div>
    <section class="call-to-action bg-purple-progress pt-64 pb-10"></section>
    <footer class="bg-purple-progress py-20 text-white text-lg">
      <div class="container mx-auto">
        <div class="sm:flex mb-4">
          <div class="sm:w-1/2 sm:mt-0 mt-8 h-auto">
            <img src="/logo-footer.svg" alt="" class="mb-3" />
            <p class="font-light">
              Helps people execute their <br />bright ideas
            </p>
          </div>
          <div class="sm:w-1/4 h-auto">
            <div class="mb-8 font-bold">Explore</div>
            <ul class="font-light">
              <li class="mb-3">Our Services</li>
              <li class="mb-3">Equity System</li>
              <li class="mb-3">Refund</li>
              <li class="mb-3">Shareholder</li>
            </ul>
          </div>
          <div class="sm:w-1/4 h-auto">
            <div class="mb-8 font-bold">Investor</div>
            <ul class="font-light">
              <li class="mb-3">My Account</li>
              <li class="mb-3">Top Startups</li>
              <li class="mb-3">How-to Tutorials</li>
              <li class="mb-3">Withdrawl</li>
            </ul>
          </div>
          <div class="sm:w-1/4 h-auto">
            <div class="mb-8 font-bold">Office</div>
            <ul class="font-light">
              <li class="mb-3">+021 2208 1996</li>
              <li class="mb-3">KBP, Bandung</li>
              <li class="mb-3">No.12 (Backer)</li>
              <li class="mb-3">support@backer.id</li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss">
.dashboard-header {
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-color: #3b41e3;
  background-size: 250px;
  height: 100px;
}

.cta-clip {
  position: relative;
  top: 200px;
  bottom: 0;
  right: 0;
  left: 0;
  width: 100%;
  height: 300px;
  background-position: top right;
  background-size: 300px;
  background-repeat: no-repeat;
  background-color: #fff;
  transform: skewY(4deg);
  transform-origin: bottom right;
}

.call-to-action {
  background-image: url('/auth-background.svg');
  background-position: top right;
  background-repeat: no-repeat;
  background-size: 450px;
}

.card-project {
  transition: all 0.3s ease 0s, opacity 0.5s cubic-bezier(0.5, 0, 0, 1) 1ms;
  max-height: 445px;
  overflow: hidden;

  .button-cta {
    opacity: 0;
    transition: all 300ms ease;
  }

  &:hover {
    box-shadow: 0 4px 25px 0 rgba(0, 0, 0, 0.15);

    .button-cta {
      opacity: 1;
      transition: all 300ms ease;
    }

    .progress-bar,
    .progress-info {
      opacity: 0;
      height: 0px;
      margin: 0px;
      padding: 0px;
      transition: all 300ms ease;
    }
  }
}

footer {
  z-index: inherit;
}

.hero-underline {
  text-decoration-color: #1abc9c;
}

.testimonial-user {
  opacity: 0.4;
  &.active {
    opacity: 1;
    border: 5px solid #fff;
    box-shadow: 0 0 0 1px #3b41e3;
  }
}

.list-check {
  li {
    background: url('/icon-checklist.svg') no-repeat left 8px;
    padding: 6px 0px 3px 28px;
  }
}

.item-thumbnail:hover {
  background-color: #ff872e;
  border-radius: 20px;
  &:after {
    position: absolute;
    top: 38%;
    left: 41%;
    content: url('/icon-thumbnail-hover.svg');
  }
  img {
    opacity: 0.3;
  }
}
</style>
