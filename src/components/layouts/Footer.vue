<template>
  <footer class="bg-red-700 text-white px-20 pt-10">
    <div class="flex">
        <div class="w-1/4">
            <img src="https://i.ibb.co/VL3mvPp/Lemon-Wares-white-Logo-1500px-wide-1.png" alt="">
            <p class="text-sm mt-4">Lorem ipsum dolor sit amet, consectetur adipiscing elit ut aliquam, purus sit amet luctus venenatis, lectus magna fringilla urna, porttitor rhoncus dolor purus non enim praesent elem</p>
        </div>
        <div class="flex-grow flex mx-20 text-md">
            <div class="w-1/4 capitalize">
                <ul>
                    <li class="font-bold mb-5">service</li>
                    <li class="font-light my-5" v-for="service in services" :key="service">
                        {{service}}
                    </li>
                </ul>
            </div>
            <div class="w-1/4 capitalize">
                <ul>
                    <li class="font-bold mb-4">hosting</li>
                    <li class="font-light my-5" v-for="hosting in hostings" :key="hosting">
                        {{hosting}}
                    </li>
                </ul>
            </div>
            <div class="w-1/4 capitalize">
                <ul>
                    <li class="font-bold mb-4">company</li>
                    <li class="font-light my-5" v-for="company in companies" :key="company">
                        {{company}}
                    </li>
                </ul>
            </div>
            <div class="w-1/4 capitalize">
                <ul>
                    <li class="font-bold mb-4">help</li>
                      <li class="font-light my-5" v-for="help in helps" :key="help">
                          {{help}}
                      </li>
                </ul>
            </div>
        </div>
    </div>
    <div class="h-28 flex place-items-center">
      <p class="text-sm">
        Coded by
        <a
          class="text-yellow-300"
          href="http://dhoniaridho.vercel.app"
          target="_blank"
          rel="noopener noreferrer"
        >dhoniaridho</a>. Copyright 2021
      </p>
    </div>
  </footer>
</template>

<script>
import { reactive, toRefs } from "@vue/reactivity";
export default {
  setup() {
    const state = reactive({
      services: [
        "Domain",
        "Shared Hosting",
        "Cloud Hosting",
        "Private Hosting",
      ],
      hostings: [
        "Cheap Hosting",
        "Hosting Wordpress",
        "Email Hosting",
        "Hosting Unlimited",
      ],
      companies: ["About", "Career", "Contact Us"],
      helps: ["FAQS", "Help support"],
    });
    return {
      ...toRefs(state),
    };
  },
};
</script>

<style>
</style>