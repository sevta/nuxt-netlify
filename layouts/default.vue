<template>
  <div
    class="main-layout dark:bg-gray-900 transition-colors duration-200 w-full min-h-screen"
  >
    <nuxt />
  </div>
</template>

<script>
export default {
  transitions: {
    name: 'my-layouts'
  }
}
</script>

<style lang="scss"></style>
