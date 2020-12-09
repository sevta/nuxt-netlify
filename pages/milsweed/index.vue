<template>
  <div class="home-wrapper">
    <Banner />
    <div class="container-full px-24 mx-auto bg-green-600 py-14 hidden">
      <div class="row">
        <div class="main-quote text-white dark:text-black ">
          <h1 class="text-5xl font-bold">
            Welcome in milsweeds
          </h1>
          <div class="text-base mt-5 font-body">
            Sayuran Hydroponik dengan Media Tanam Air Minum
          </div>
        </div>
      </div>
    </div>
    <div class="container-full px-24 mx-auto py-10 bg-green-700 text-white">
      <div class="row">
        <div class="why grid grid-cols-3 gap-3">
          <div v-for="item in 3" :key="item">
            <div class="font-bold text-2xl uppercase mb-2">
              Kenapa
            </div>
            <div class="font-body text-sm leading-relaxed">
              Lorem ipsum dolor sit amet consectetur adipisicing elit. Nam,
              consectetur distinctio, in maiores voluptas quos adipisci qui quod
              itaque, nemo alias dolor. Eius sit aut omnis amet perspiciatis,
              quod deserunt!
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: 'milsweed',
  mounted() {
    this.loadDarkMode()
  },
  methods: {
    loadDarkMode() {
      if (
        localStorage.theme === 'dark' ||
        (!('theme' in localStorage) &&
          window.matchMedia('(prefers-color-scheme: dark)').matches)
      ) {
        document.querySelector('html').classList.add('dark')
      } else {
        document.querySelector('html').classList.remove('dark')
      }

      localStorage.theme = 'light'
    }
  }
}
</script>

<style lang="postcss" scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
  @apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
