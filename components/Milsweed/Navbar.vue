<template>
  <nav class="fixed top-0 w-full z-10">
    <div class="container mx-auto py-7">
      <div class="row flex flex-wrap" v-if="type == 'type-1'">
        <div class="logo col flex-1 text-3xl text-white font-black uppercase">
          <NuxtLink to="/" class="link-logo flex">
            <span class="">mils</span>
            <span class="text-green-200">weeds</span>
          </NuxtLink>
        </div>

        <div class="col flex-1 flex justify-end items-center">
          <div class="flex">
            <NuxtLink
              v-for="(item, index) in menus"
              :key="index"
              :to="item.link"
              class="ml-10 text-base font-semibold text-white capitalize font-body cursor-pointer dark:text-white"
            >
              {{ item.label }}
            </NuxtLink>
          </div>
        </div>
      </div>
      <div class="row flex items-center justify-center" v-if="type == 'type-2'">
        <div class="flex">
          <NuxtLink
            v-for="(item, index) in menus"
            :key="index"
            :to="item.link"
            class="ml-10 text-base font-semibold capitalize font-body cursor-pointer dark:text-white"
          >
            {{ item.label }}
          </NuxtLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'type-1'
    }
  },
  data: () => ({
    menus: [
      {
        label: 'home',
        link: '/milsweed'
      },
      {
        label: 'blog',
        link: '/milsweed/blog'
      },
      {
        label: 'product',
        link: '/milsweed/product'
      },
      {
        label: 'about',
        link: '/milsweed/about'
      },
      {
        label: 'where to buy',
        link: '/milsweed/storelocator'
      },
      {
        label: 'contact-us',
        link: '/milsweed/contact-us'
      }
    ]
  })
}
</script>

<style lang="postcss" scoped>
.nuxt-link-exact-active {
  @apply text-green-500;
  background-color: white;
  border-radius: 3px;
  padding: 0px 5px;
}
.link-logo {
  color: white;
  background-color: transparent;
  padding: 0;
  border-radius: 0;
}
</style>
