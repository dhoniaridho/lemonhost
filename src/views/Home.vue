<template>
  <default-layout>
    <section class="h-[calc(100vh-6rem)] flex justify-between py-10 px-20">
      <div class="w-1/2">
        <div class="font-semibold">
          <div
            role="button"
            @click="handleService(service)"
            :class="
              getService === service
                ? 'border-red-700 text-red-700'
                : 'text-gray-400'
            "
            class="
              block
              text-sm
              py-1
              lg:inline-block
              border-b-2
              lg:mt-0
              px-2
              hover:text-red-600
              font-semibold
            "
            v-for="service in services"
            :key="service"
          >
            {{ service }}
          </div>
        </div>
        <div class="mt-5">
          <h1 class="text-5xl font-extrabold">
            Premium Web <br />
            Hosting for Your <br />
            Website
          </h1>
        </div>
        <div class="my-8 text-gray-500">
          <p>
            Blazing fast web hosting for individuals and <br />
            businesses of all sizes backed by 24x7x365 Support.
          </p>
        </div>
        <div class="mt-10">
          <Link
            class="text-sm md:text-md mr-2 shadow-red"
            type="primary"
            href="/"
          >
            Create an Account
          </Link>
          <Link class="text-sm md:text-md mr-2" type="secondary" href="/">
            Choose your plan
          </Link>
        </div>
      </div>
      <div class="w-1/2">
        <img
          class="object-scale-down"
          src="https://i.ibb.co/QQ6Gqgn/hero.png"
        />
      </div>
    </section>
    <section class="flex flex-col px-20 py-20">
      <div class="flex justify-between mt-10">
        <div class="w-1/2">
          <h1 class="text-4xl font-bold">True Cloud Web Hosting</h1>
          <p class="mt-8 text-sm w-3/4">
            True Cloud Web Hosting All of the hosting packages we offer are
            deployed instantly on our SSD powered cloud. We don’t use dedicated
            servers that operate on single pieces of hardware. Our entire
            infrastructure is built to be reliable, secure, and scalable.
          </p>
        </div>
        <div class="w-1/2 grid grid-cols-3 gap-8">
          <div>
            <img src="https://i.ibb.co/pJwRL1K/1.png" alt="provider" />
          </div>
          <div>
            <img src="https://i.ibb.co/1TDtLMz/2.png" alt="provider" />
          </div>
          <div>
            <img src="https://i.ibb.co/zRQPdJP/3.png" alt="provider" />
          </div>
          <div>
            <img src="https://i.ibb.co/YprsB29/4.png" alt="provider" />
          </div>
          <div>
            <img src="https://i.ibb.co/HqRrFR1/5.png" alt="provider" />
          </div>
          <div>
            <img src="https://i.ibb.co/pJwRL1K/1.png" alt="provider" />
          </div>
        </div>
      </div>
      <div class="grid grid-flow-col gap-5 py-20 px-10">
        <div
          class="text-center"
          v-for="solution in solutions"
          :key="solution.title"
        >
          <img
            class="w-1/4 mx-auto"
            :src="solution.image"
            :alt="solution.title"
          />
          <h3 class="font-extrabold mt-3">{{ solution.title }}</h3>
          <p class="text-xs text-gray-500 mt-2">{{ solution.paragraph }}</p>
        </div>
      </div>
    </section>
    <section class="py-10 px-20">
      <div class="text-center">
        <h1 class="text-4xl font-bold">
          Ready to get started with <br />
          Lemon Wares?
        </h1>
        <h4 class="text-xl mt-5">Choose the package that suits you</h4>
        <div class="mt-7 flex justify-center place-items-center">
          <div class="flex place-items-center">
            <div>
            <h1>Monthly</h1>
            </div>
          </div>
          <label class="switch mx-10">
            <input type="checkbox" checked />
            <span class="slider round"></span>
          </label>
          <div class="flex place-items-center">
            <h1>Yearly</h1>
          </div>
          <span class="text-xs absolute scale-90 -mr-96 inline bg-yellow-400 rounded-full p-1 text-gray-800"
            >20% discount</span>
        </div>
        <div class="text-3xl font-bold flex justify-center my-20">
          <h1 @click="setSubscription('Basic')" role="button" :class="subscription === 'Basic' ? 'border-red-700' : 'border-gray-400'" class="border-b-2 px-16">Basic</h1>
          <h1 @click="setSubscription('Premium')" role="button" :class="subscription === 'Premium' ? 'border-red-700' : 'border-gray-400'" class="border-b-2 px-16">Premium</h1>
        </div>
        <div class="flex justify-around">
          <div v-for="p in pricing" :key="p" class="border w-1/3 mx-10 text-left p-5 rounded-lg">
            <div>
              <h1 class="text-3xl font-bold">{{p.title}}</h1>
              <p class="text-xs mt-2">with all your customers via all conversation channels in one central dashboard.</p>
            </div>
            <div class="mt-6">
              <h1 class="text-3xl font-bold">{{p.price}}</h1>
              <p class="text-sm font-light">Per month</p>
              <Link class="block text-center my-8" href="/" type="secondary">
                Choose this Plan
              </Link>
            </div>
            <ul class="mt-5 text-gray-500">
              <li v-for="feature in p.features" :key="feature" class="my-3 flex">
                  <CheckIcon class="w-5 mr-10" />
                <p>{{feature}}</p>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </default-layout>
</template>

<script>

import { onMounted, reactive, toRefs } from "vue";
import { CheckIcon } from '@heroicons/vue/outline'
import DefaultLayout from "../components/layouts/DefaultLayout.vue";
import Link from "../components/ui/Link.vue";

export default {
  components: { DefaultLayout, Link, CheckIcon },
  name: "Home",
  setup() {
    const state = reactive({
      numb: 0,
      subscription: "Basic",
      getService: "Hosting",
      services: ["Hosting", "Domain", "SEO", "Email"],
      solutions: [
        {
          image: "https://i.ibb.co/HVm0yJN/uptime.png",
          title: "99.9% Uptime",
          paragraph:
            "We Keep Your Web build Online 24x7x365. Downtime not only costs you lost visitors but also damages your reputation and search engine rankings.",
        },
        {
          image: "https://i.ibb.co/jGLpjsQ/blazing.png",
          title: "99.9% Uptime",
          paragraph:
            "We Keep Your Web build Online 24x7x365. Downtime not only costs you lost visitors but also damages your reputation and search engine rankings.",
        },
        {
          image: "https://i.ibb.co/1Xfb8z8/ssl.png",
          title: "99.9% Uptime",
          paragraph:
            "We Keep Your Web build Online 24x7x365. Downtime not only costs you lost visitors but also damages your reputation and search engine rankings.",
        },
        {
          image: "https://i.ibb.co/M17vTzR/support.png",
          title: "99.9% Uptime",
          paragraph:
            "We Keep Your Web build Online 24x7x365. Downtime not only costs you lost visitors but also damages your reputation and search engine rankings.",
        },
      ],
      pricing: [
        {
          title: "Starter",
          price: "$2.80",
          description: "with all your customers via all conversation channels in one central dashboard.",
          features: ["2 GB SSD", "10GB Bandwidth", "15 Email Accounts", "Unlimited Database", "4 Subdomains", "1 Parked Domain", "2 Websites", "Free SSL", "Softaculous"]
        },
        {
          title: "Standard",
          price: "$4.20",
          description: "with all your customers via all conversation channels in one central dashboard.",
          features: ["2 GB SSD", "10GB Bandwidth", "15 Email Accounts", "Unlimited Database", "4 Subdomains", "1 Parked Domain", "2 Websites", "Free SSL", "Softaculous"]
        },
        {
          title: "Suprem",
          price: "$7.00",
          description: "with all your customers via all conversation channels in one central dashboard.",
          features: ["2 GB SSD", "10GB Bandwidth", "15 Email Accounts", "Unlimited Database", "4 Subdomains", "1 Parked Domain", "2 Websites", "Free SSL", "Softaculous"]
        },
      ]
    });

    const handleService = (selected) => {
      state.getService = selected;
    };

    const setSubscription = (selected) => {
      state.subscription = selected;
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
      setSubscription,
      handleService,
      ...toRefs(state),
    };
  },
};
</script>
