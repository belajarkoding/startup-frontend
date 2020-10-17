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
      <div class="flex justify-between items-center mb-6">
        <div class="w-3/4 mr-6">
          <h2 class="text-4xl text-gray-900 mb-2 font-medium">Dashboard</h2>
          <ul class="flex mt-2">
            <li class="mr-6">
              <nuxt-link
                class="text-gray-500 hover:text-gray-800"
                to="/dashboard"
              >
                Your Projects
              </nuxt-link>
            </li>
            <li class="mr-6">
              <a class="text-gray-800 font-bold" href="#">
                Your Transactions
              </a>
            </li>
          </ul>
        </div>
      </div>
      <hr />
      <div class="block mb-2">
        <div class="w-full lg:max-w-full lg:flex mb-4" v-for="i in 5" :key="i">
          <div
            class="h-48 lg:h-auto lg:w-48 flex-none bg-cover rounded-t lg:rounded-t-none lg:rounded-l text-center overflow-hidden"
            style="background-color: #bbb"
          ></div>
          <div
            class="w-full border-r border-b border-l border-gray-400 lg:border-l-0 lg:border-t lg:border-gray-400 bg-white rounded-b lg:rounded-b-none lg:rounded-r p-8 flex flex-col justify-between leading-normal"
          >
            <div>
              <div class="text-gray-900 font-bold text-xl mb-1">
                Cari Uang Buat Gunpla
              </div>
              <p class="text-sm text-gray-600 flex items-center mb-2">
                Rp. 200.000.000 &middot; 12 September 2020
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
