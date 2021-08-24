<template>
  <div>
      <Navigation/>
      <main>
          <slot/>
      </main>
      <Footer />
  </div>
</template>

<script>

import Navigation from './Navigation.vue'
import Footer from './Footer.vue'

export default {
  components: { Navigation, Footer },

}
</script>

<style>

</style>