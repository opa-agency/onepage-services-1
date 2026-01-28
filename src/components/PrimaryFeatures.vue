<template>
  <section
    id="features"
    aria-label="Features for running your books"
    class="relative overflow-hidden bg-gradient-to-br from-blue-600 via-blue-600 to-purple-600 pt-20 pb-28 sm:py-32"
  >
    <img
      class="absolute top-1/2 left-1/2 max-w-none translate-x-[-44%] translate-y-[-42%]"
      src="/images/background-features.jpg"
      alt=""
      loading="lazy"
      onerror="this.style.opacity='0'"
    />
    <Container class="relative">
      <div class="max-w-2xl md:mx-auto md:text-center xl:max-w-none">
        <h2 class="font-display text-3xl tracking-tight text-white sm:text-4xl md:text-5xl">
          Everything you need to run your books.
        </h2>
        <p class="mt-6 text-lg tracking-tight text-blue-100">
          Well everything you need if you aren't that picky about minor
          details like tax compliance.
        </p>
      </div>
      <div class="mt-16 grid grid-cols-1 items-center gap-y-2 pt-10 sm:gap-y-6 md:mt-20 lg:grid-cols-12 lg:pt-0">
        <div class="-mx-4 flex overflow-x-auto pb-4 sm:mx-0 sm:overflow-visible sm:pb-0 lg:col-span-5">
          <div class="relative z-10 flex gap-x-4 px-4 whitespace-nowrap sm:mx-auto sm:px-0 lg:mx-0 lg:block lg:gap-x-0 lg:gap-y-1 lg:whitespace-normal">
            <button
              v-for="(feature, index) in features"
              :key="feature.title"
              @click="selectedIndex = index"
              :class="[
                'group relative rounded-full px-4 py-1 lg:rounded-l-xl lg:rounded-r-none lg:p-6',
                selectedIndex === index
                  ? 'bg-white lg:bg-white/10 lg:ring-1 lg:ring-white/10 lg:ring-inset'
                  : 'hover:bg-white/10 lg:hover:bg-white/5',
              ]"
            >
              <h3>
                <span
                  :class="[
                    'font-display text-lg data-selected:not-data-focus:outline-hidden',
                    selectedIndex === index
                      ? 'text-blue-600 lg:text-white'
                      : 'text-blue-100 hover:text-white lg:text-white',
                  ]"
                >
                  <span class="absolute inset-0 rounded-full lg:rounded-l-xl lg:rounded-r-none" />
                  {{ feature.title }}
                </span>
              </h3>
              <p
                :class="[
                  'mt-2 hidden text-sm lg:block',
                  selectedIndex === index
                    ? 'text-white'
                    : 'text-blue-100 group-hover:text-white',
                ]"
              >
                {{ feature.description }}
              </p>
            </button>
          </div>
        </div>
        <div class="lg:col-span-7">
          <div v-if="selectedFeature" class="relative sm:px-6 lg:hidden">
            <div class="absolute -inset-x-4 -top-26 -bottom-17 bg-white/10 ring-1 ring-white/10 ring-inset sm:inset-x-0 sm:rounded-t-xl" />
            <p class="relative mx-auto max-w-2xl text-base text-white sm:text-center">
              {{ selectedFeature.description }}
            </p>
          </div>
          <div class="mt-10 w-[45rem] overflow-hidden rounded-xl bg-slate-50 shadow-xl shadow-blue-900/20 sm:w-auto lg:mt-0 lg:w-[67.8125rem]">
            <img
              v-if="selectedFeature"
              :key="selectedFeature.image"
              :src="selectedFeature.image"
              alt="Feature screenshot"
              loading="eager"
              class="w-full h-auto"
            />
          </div>
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'
import Container from './Container.vue'

const selectedIndex = ref(0)

const features = [
  {
    title: 'Payroll',
    description:
      "Keep track of everyone's salaries and whether or not they've been paid. Direct deposit not supported.",
    image: '/images/screenshots/payroll.png',
  },
  {
    title: 'Claim expenses',
    description:
      "All of your receipts organized into one place, as long as you don't mind typing in the data by hand.",
    image: '/images/screenshots/expenses.png',
  },
  {
    title: 'VAT handling',
    description:
      "We only sell our software to companies who don't deal with VAT at all, so technically we do all the VAT stuff they need.",
    image: '/images/screenshots/vat-returns.png',
  },
  {
    title: 'Reporting',
    description:
      'Easily export your data into an Excel spreadsheet where you can do whatever the hell you want with it.',
    image: '/images/screenshots/reporting.png',
  },
]

const selectedFeature = computed(() => features[selectedIndex.value])
</script>
