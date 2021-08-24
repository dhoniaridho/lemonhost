<template>
  <default-layout>
    <section class="h-[calc(100vh-6rem)] flex justify-between py-10 px-20">
      <div class="w-1/2">
        <div class="font-semibold">
          <div
            role="button"
            @click="handleService(service)"
            :class="
              getService === service ? 'border-red-700 text-red-700' : 'text-gray-400'
            "
            class="block py-1 lg:inline-block border-b-2 lg:mt-0 px-2 hover:text-red-600 font-semibold"
            v-for="service in services"
            :key="service"
          >
            {{ service }}
          </div>
        </div>
        <div class="mt-5">
          <h1 class="text-5xl font-extrabold">
            Premium Web <br/> Hosting for Your <br/> Website
          </h1>
        </div>
        <div class="my-8 text-gray-500">
          <p>Blazing fast web hosting for individuals and <br/> businesses of all sizes backed by 24x7x365 Support.</p>
        </div>
        <div class="mt-10">
          <Link class="text-sm md:text-md mr-2 shadow-red" type="primary" href="/">
            Create an Account
          </Link>
          <Link class="text-sm md:text-md mr-2" type="secondary" href="/">
            Choose your plan
          </Link>
        </div>
      </div>
      <div class="w-1/2">
        <img class="object-scale-down" src="https://i.ibb.co/QQ6Gqgn/hero.png" />
      </div>
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
      getService: "Hosting",
      services: ["Hosting", "Domain", "SEO", "Email"],
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
