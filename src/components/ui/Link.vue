<template>
  <router-link :class="classNames" class="p-2 rounded-md" :to="href">
      <slot/>
  </router-link>
</template>

<script>
export default {
    props: {
        href: String,
        type: String
    },
    computed: {
        classNames() {
            return {
                'bg-red-700 text-white': this.$props.type === 'primary',
                'bg-transparent border border-gray-900 hover:bg-red-700 hover:border-red-700 hover:text-white': this.$props.type === 'secondary',
            }
        }
    }
}
</script>

<style>

</style>