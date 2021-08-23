<template>
  <default-layout>
    <div class="home">
      <h1>{{ numb }}</h1>
    </div>
  </default-layout>
</template>

<script>
import { onMounted, reactive, toRefs } from "vue";
import DefaultLayout from "../components/layouts/DefaultLayout.vue";

export default {
  components: { DefaultLayout },
  name: "Home",
  setup() {
    const state = reactive({
      numb: 0,
    });

    const increment = () => {
      setInterval(() => {
        state.numb++;
      }, 1000);
    };

    onMounted(() => {
      increment();
    });
    return {
      ...toRefs(state),
    };
  },
};
</script>
