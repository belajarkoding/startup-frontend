<template>
  <div class="project-page">
    <section class="dashboard-header pt-5">
      <div class="container mx-auto relative">
        <Navbar />
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
            :to="{
              name: 'dashboard-projects-id-edit',
              params: { id: campaign.data.id },
            }"
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
                {{ campaign.data.name }}
              </div>
              <p class="text-gray-700 text-base">
                {{ campaign.data.short_description }}
              </p>
              <p class="text-sm font-bold flex items-center mb-1 mt-4">
                Description
              </p>
              <p class="text-gray-700 text-base">
                {{ campaign.data.description }}
              </p>
              <p class="text-sm font-bold flex items-center mb-1 mt-4">
                What Will Funders Get
              </p>
              <ul class="list-disc ml-5">
                <li v-for="perk in campaign.data.perks" :key="perk">
                  {{ perk }}
                </li>
              </ul>
              <p class="text-sm font-bold flex items-center mb-1 mt-4">
                Goal Amount
              </p>
              <p class="text-4xl text-gray-700 text-base">
                {{ new Intl.NumberFormat().format(campaign.data.goal_amount) }}
              </p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="w-2/4 mr-6">
          <h3 class="text-2xl text-gray-900 mb-4 mt-5">Gallery</h3>
        </div>
        <div class="w-2/4 text-right">
          <input
            type="file"
            ref="file"
            @change="selectFile"
            class="border p-1 rounded overflow-hidden"
          />
          <button
            @click="upload"
            class="bg-green-button hover:bg-green-button text-white font-bold px-4 py-2 rounded inline-flex items-center"
          >
            Upload
          </button>
        </div>
      </div>
      <div class="grid grid-cols-4 gap-4 -mx-2">
        <div
          class="relative w-full bg-white m-2 p-2 border border-gray-400 rounded"
          v-for="image in campaign.data.images"
          :key="image.image_url"
        >
          <figure class="item-thumbnail">
            <img
              :src="$axios.defaults.baseURL + '/' + image.image_url"
              alt=""
              class="rounded w-full"
            />
          </figure>
        </div>
      </div>
      <div class="flex justify-between items-center">
        <div class="w-3/4 mr-6">
          <h3 class="text-2xl text-gray-900 mb-4 mt-5">Transaction History</h3>
        </div>
      </div>
      <div class="block mb-2">
        <div
          class="w-full lg:max-w-full lg:flex mb-4"
          v-for="transaction in transactions.data"
          :key="transaction.id"
        >
          <div
            class="w-full border border-gray-400 lg:border-gray-400 bg-white rounded p-8 flex flex-col justify-between leading-normal"
          >
            <div>
              <div class="text-gray-900 font-bold text-xl mb-1">
                {{ transaction.name }}
              </div>
              <p class="text-sm text-gray-600 flex items-center mb-2">
                Rp.
                {{ new Intl.NumberFormat().format(transaction.amount) }}
                &middot; {{ transaction.created_at }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="cta-clip -mt-20"></div>
    <section class="call-to-action bg-purple-progress pt-64 pb-10"></section>
    <Footer />
  </div>
</template>

<script>
export default {
  middleware: 'auth',
  async asyncData({ $axios, params }) {
    const campaign = await $axios.$get('/api/v1/campaigns/' + params.id)
    const transactions = await $axios.$get(
      '/api/v1/campaigns/' + params.id + '/transactions'
    )
    return { campaign, transactions }
  },
  data() {
    return {
      selectedFiles: undefined,
    }
  },
  methods: {
    selectFile() {
      this.selectedFiles = this.$refs.file.files
    },
    async load() {
      const campaign = await this.$axios.$get(
        '/api/v1/campaigns/' + this.$route.params.id
      )
      this.campaign = campaign
    },
    async upload(file) {
      let formData = new FormData()

      formData.append('campaign_id', this.$route.params.id)
      formData.append('file', this.selectedFiles.item(0))
      formData.append('is_primary', true)

      try {
        let response = await this.$axios.post(
          '/api/v1/campaign-images',
          formData,
          {
            headers: {
              'Content-Type': 'multipart/form-data',
            },
          }
        )
        console.log(response)

        this.load()
        this.selectedFiles = undefined
      } catch (err) {
        console.log(err)
      }
    },
  },
}
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
  max-height: 485px;
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
