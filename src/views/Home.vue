<template>
  <default-layout>
    <section class="h-[calc(100vh-4rem)] flex justify-between place-items-center">
      <div class="w-1/2">
        <div class="grid grid-flow-col gap-3">
          <div
            role="button"
            @click="handleService(service)"
            :class="
              getService === service ? 'border-red-700' : 'border-transparent'
            "
            class="border-b-2"
            v-for="service in services"
            :key="service"
          >
            {{ service }}
          </div>
        </div>
        <div></div>
        <div></div>
        <div class="mt-5">
          <Link class="text-sm mr-2" type="primary" href="/">
            Create an Account
          </Link>
          <Link class="text-sm mr-2" type="secondary" href="/">
            Choose your plan
          </Link>
        </div>
      </div>
      <div></div>
    </section>
  </default-layout>
</template>

<script>
import { onMounted, reactive, toRefs } from "vue";
import DefaultLayout from "../components/layouts/DefaultLayout.vue";
import Link from "../components/ui/Link.vue";

export default {
  components: { DefaultLayout, Link },
  name: "Home",
  setup() {
    const state = reactive({
      numb: 0,
      getService: "",
      services: ["hosting", "domain", "seo", "email"],
    });

    const handleService = (selected) => {
      state.getService = selected;
    };

    const increment = () => {
      setInterval(() => {
        state.numb++;
      }, 1000);
    };

    onMounted(() => {
      increment();
    });
    return {
      handleService,
      ...toRefs(state),
    };
  },
};
</script>
