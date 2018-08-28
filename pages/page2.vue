<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        nuxt-lifecycle-example
      </h1>
      <h2 class="subtitle">
        <nuxt-link to="/">index</nuxt-link>
      </h2>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'

export default {
  middleware: ['page2', 'page1'],
  components: {
    AppLogo
  },
  created() {
    console.log("page2 created")
  },
  mounted() {
    console.log("page2 mounted")
  },
  fetch (context) {
    console.log("page2 fetch")
  },
  validate (context) {
    console.log("page2 validate")
    return true
  },
  asyncData (context) {
    console.log("page2 asyncData")
  }
}
</script>
