<template>
  <div class="w-full min-h-screen p-10">
    <button
      class="cursor-pointer focus:outline-none border-0"
      @click="toggleDarkMode"
    >
      <svg
        class="w-6 h-6 dark:text-white text-gray-900 outline-none"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M20.354 15.354A9 9 0 018.646 3.646 9.003 9.003 0 0012 21a9.003 9.003 0 008.354-5.646z"
        ></path>
      </svg>
    </button>
    <div class="container px-5 lg:px-52 mx-auto mt-5 font-caveat">
      <div class="row flex flex-col divide-y-2 dark:divide-gray-600">
        <div
          class="notes-lists py-10"
          v-for="(item, index) in articles"
          :key="index"
        >
          <h1 class="font-caveat text-7xl capitalize mb-5 dark:text-gray-50">
            {{ item.body.children[0].children[1].value }}
          </h1>

          <p class="dark:text-gray-200  text-2xl">
            {{ item.body.children[2].children[0].value }}
          </p>
          <div class="flex mt-7">
            <nuxt-link
              :to="'notes/' + item.slug"
              class="border rounded-sm border-gray-400 dark:text-gray-200 font-bold px-10 py-2 text-xl capitalize"
            >
              open
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'notes',
  async asyncData({ $content }) {
    const articles = await $content('articles').fetch()
    return {
      articles
    }
  },
  data() {
    return {
      darkMode: false
    }
  },
  mounted() {
    console.log(this.articles)
  },
  watch: {
    darkMode(darkMode) {
      if (darkMode) {
        document.querySelector('html').classList.add('dark')
      } else {
        document.querySelector('html').classList.remove('dark')
      }
    }
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode
    }
  }
}
</script>
