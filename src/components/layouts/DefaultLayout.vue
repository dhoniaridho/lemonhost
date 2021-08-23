<template>
  <div>
      <Navigation/>
      <main>
          <slot/>
      </main>
  </div>
</template>

<script>
import Navigation from './Navigation.vue'
export default {
  components: { Navigation },

}
</script>

<style>

</style>