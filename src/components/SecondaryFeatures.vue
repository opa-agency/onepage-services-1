<template>
  <section
    id="secondary-features"
    aria-label="Features for simplifying everyday business tasks"
    class="pt-20 pb-14 sm:pt-32 sm:pb-20 lg:pb-32"
  >
    <Container>
      <div class="mx-auto max-w-2xl md:text-center">
        <h2 class="font-display text-3xl tracking-tight text-slate-900 sm:text-4xl">
          Simplify everyday business tasks.
        </h2>
        <p class="mt-4 text-lg tracking-tight text-slate-700">
          Because you'd probably be a little confused if we suggested you
          complicate your everyday business tasks instead.
        </p>
      </div>

      <!-- Mobile view -->
      <div class="-mx-4 mt-20 flex flex-col gap-y-10 overflow-hidden px-4 sm:-mx-6 sm:px-6 lg:hidden">
        <div v-for="feature in features" :key="feature.name">
          <div class="mx-auto max-w-2xl">
            <div class="w-9 rounded-lg bg-blue-600">
              <svg aria-hidden="true" class="h-9 w-9" fill="none" viewBox="0 0 40 40">
                <template v-if="feature.icon === 'reporting'">
                  <defs>
                    <linearGradient id="reportingGradient" x1="11.5" y1="18" x2="36" y2="15.5" gradientUnits="userSpaceOnUse">
                      <stop offset=".194" stop-color="#fff" />
                      <stop offset="1" stop-color="#6692F1" />
                    </linearGradient>
                  </defs>
                  <path d="m30 15-4 5-4-11-4 18-4-11-4 7-4-5" stroke="url(#reportingGradient)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                </template>
                <template v-else-if="feature.icon === 'inventory'">
                  <path opacity=".5" d="M8 17a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                  <path opacity=".3" d="M8 24a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                  <path d="M8 10a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                </template>
                <template v-else-if="feature.icon === 'contacts'">
                  <path opacity=".5" d="M25.778 25.778c.39.39 1.027.393 1.384-.028A11.952 11.952 0 0 0 30 18c0-6.627-5.373-12-12-12S6 11.373 6 18c0 2.954 1.067 5.659 2.838 7.75.357.421.993.419 1.384.028.39-.39.386-1.02.036-1.448A9.959 9.959 0 0 1 8 18c0-5.523 4.477-10 10-10s10 4.477 10 10a9.959 9.959 0 0 1-2.258 6.33c-.35.427-.354 1.058.036 1.448Z" fill="#fff" />
                  <path d="M12 28.395V28a6 6 0 0 1 12 0v.395A11.945 11.945 0 0 1 18 30c-2.186 0-4.235-.584-6-1.605ZM21 16.5c0-1.933-.5-3.5-3-3.5s-3 1.567-3 3.5 1.343 3.5 3 3.5 3-1.567 3-3.5Z" fill="#fff" />
                </template>
              </svg>
            </div>
            <h3 class="mt-6 text-sm font-medium text-blue-600">{{ feature.name }}</h3>
            <p class="mt-2 font-display text-xl text-slate-900">{{ feature.summary }}</p>
            <p class="mt-4 text-sm text-slate-600">{{ feature.description }}</p>
          </div>
          <div class="relative mt-10 pb-10">
            <div class="absolute -inset-x-4 top-8 bottom-0 bg-slate-200 sm:-inset-x-6" />
            <div class="relative mx-auto max-w-2xl overflow-hidden rounded-xl bg-white shadow-lg ring-1 shadow-slate-900/5 ring-slate-500/10">
              <img :src="feature.image" alt="" class="w-full" />
            </div>
          </div>
        </div>
      </div>

      <!-- Desktop view with tabs -->
      <div class="hidden lg:mt-20 lg:block">
        <div class="grid grid-cols-3 gap-x-8">
          <button
            v-for="(feature, featureIndex) in features"
            :key="feature.name"
            type="button"
            @click="selectedIndex = featureIndex"
            class="relative text-left"
          >
            <div :class="{ 'opacity-75 hover:opacity-100': featureIndex !== selectedIndex }">
              <div :class="['w-9 rounded-lg', featureIndex === selectedIndex ? 'bg-blue-600' : 'bg-slate-500']">
                <svg aria-hidden="true" class="h-9 w-9" fill="none" viewBox="0 0 40 40">
                  <template v-if="feature.icon === 'reporting'">
                    <defs>
                      <linearGradient id="reportingGradient2" x1="11.5" y1="18" x2="36" y2="15.5" gradientUnits="userSpaceOnUse">
                        <stop offset=".194" stop-color="#fff" />
                        <stop offset="1" stop-color="#6692F1" />
                      </linearGradient>
                    </defs>
                    <path d="m30 15-4 5-4-11-4 18-4-11-4 7-4-5" stroke="url(#reportingGradient2)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" />
                  </template>
                  <template v-else-if="feature.icon === 'inventory'">
                    <path opacity=".5" d="M8 17a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                    <path opacity=".3" d="M8 24a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                    <path d="M8 10a1 1 0 0 1 1-1h18a1 1 0 0 1 1 1v2a1 1 0 0 1-1 1H9a1 1 0 0 1-1-1v-2Z" fill="#fff" />
                  </template>
                  <template v-else-if="feature.icon === 'contacts'">
                    <path opacity=".5" d="M25.778 25.778c.39.39 1.027.393 1.384-.028A11.952 11.952 0 0 0 30 18c0-6.627-5.373-12-12-12S6 11.373 6 18c0 2.954 1.067 5.659 2.838 7.75.357.421.993.419 1.384.028.39-.39.386-1.02.036-1.448A9.959 9.959 0 0 1 8 18c0-5.523 4.477-10 10-10s10 4.477 10 10a9.959 9.959 0 0 1-2.258 6.33c-.35.427-.354 1.058.036 1.448Z" fill="#fff" />
                    <path d="M12 28.395V28a6 6 0 0 1 12 0v.395A11.945 11.945 0 0 1 18 30c-2.186 0-4.235-.584-6-1.605ZM21 16.5c0-1.933-.5-3.5-3-3.5s-3 1.567-3 3.5 1.343 3.5 3 3.5 3-1.567 3-3.5Z" fill="#fff" />
                  </template>
                </svg>
              </div>
              <h3 :class="['mt-6 text-sm font-medium', featureIndex === selectedIndex ? 'text-blue-600' : 'text-slate-600']">
                {{ feature.name }}
              </h3>
              <p class="mt-2 font-display text-xl text-slate-900">{{ feature.summary }}</p>
              <p class="mt-4 text-sm text-slate-600">{{ feature.description }}</p>
            </div>
          </button>
        </div>

        <!-- Carousel container -->
        <div class="relative mt-20 overflow-hidden rounded-4xl bg-slate-200 px-14 py-16 xl:px-16">
          <div class="-mx-5 flex transition duration-500 ease-in-out" :style="{ transform: `translateX(calc(-${selectedIndex} * 52.75rem))` }">
            <div
              v-for="(feature, featureIndex) in features"
              :key="feature.name"
              class="w-[52.75rem] flex-shrink-0 px-5"
              :class="{ 'opacity-60': featureIndex !== selectedIndex }"
            >
              <div class="overflow-hidden rounded-xl bg-white shadow-lg ring-1 shadow-slate-900/5 ring-slate-500/10">
                <img :key="feature.image" :src="feature.image" alt="Feature screenshot" loading="eager" class="w-full" />
              </div>
            </div>
          </div>
          <div class="pointer-events-none absolute inset-0 rounded-4xl ring-1 ring-slate-900/10 ring-inset" />
        </div>
      </div>
    </Container>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import Container from './Container.vue'

const selectedIndex = ref(0)

const features = [
  {
    name: 'Reporting',
    summary: 'Stay on top of things with always up-to-date reporting features.',
    description:
      'We talked about reporting in the section above but we needed three items here, so mentioning it one more time for posterity.',
    image: '/images/screenshots/profit-loss.png',
    icon: 'reporting',
  },
  {
    name: 'Inventory',
    summary: 'Never lose track of what\'s in stock with accurate inventory tracking.',
    description:
      'We don\'t offer this as part of our software but that statement is inarguably true. Accurate inventory tracking would help you for sure.',
    image: '/images/screenshots/inventory.png',
    icon: 'inventory',
  },
  {
    name: 'Contacts',
    summary: 'Organize all of your contacts, service providers, and invoices in one place.',
    description:
      'This also isn\'t actually a feature, it\'s just some friendly advice. We definitely recommend that you do this, you\'ll feel really organized and professional.',
    image: '/images/screenshots/contacts.png',
    icon: 'contacts',
  },
]
</script>
