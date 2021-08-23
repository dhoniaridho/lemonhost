<template>
  <header>
      <nav class="px-20 bg-white shadow-md">
          <div class="h-16 w-full flex place-items-center justify-between">
                <div>
                    a
                </div>
                <div class="flex justify-around">
                    <div class="mx-1">
                        <a href="#">About</a>
                    </div>
                    <div class="mx-1">
                        <a href="#">Blog</a>
                    </div>
                    <div class="mx-1">
                        <a href="#">Contact</a>
                    </div>
                </div>
                <div class="flex justify-around">
                    <div class="mx-1">
                        <a href="#">Login</a>
                    </div>
                    <div class="mx-1">
                        <a href="#">Register</a>
                    </div>
                </div>
                <div class="sm:hidden">
                    <button class="focus:outline-none" @click="handleClick()">
                        <MenuAlt3Icon class="h-5 w-5 text-blue-500"/>
                    </button>
                </div>
          </div>
      </nav>
      <div @click="handleClick()" :class="isCollapse ? 'translate-x-0' : 'translate-x-full'" class="fixed transition-all transform w-full h-screen bg-blue-400 inset-0">

      </div>
  </header>
</template>

<script>
import { reactive, toRefs } from '@vue/reactivity'
import { MenuAlt3Icon } from '@heroicons/vue/outline'

export default {
    name: 'Navigation',
    components: {
        MenuAlt3Icon
    },
    setup () {
        const state = reactive({
            isCollapse: false
        })
        function handleClick() {
            state.isCollapse = !state.isCollapse
        }
        return {
            handleClick,
            ...toRefs(state)
        }
    }
}
</script>