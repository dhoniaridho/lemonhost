<template>
  <router-link :class="classNames" class="py-2 px-5 rounded-md" :to="href">
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
                'bg-red-700 hover:bg-red-800 text-white border-red-700 hover:border-red-800': this.$props.type === 'primary',
                'bg-transparent border border-gray-900 hover:bg-red-700 hover:border-red-700 hover:text-white': this.$props.type === 'secondary',
            }
        }
    }
}
</script>

<style>

</style>