<template>
  <header class="py-10">
    <Container>
      <nav class="relative z-50 flex justify-between">
        <div class="flex items-center md:gap-x-12">
          <a href="#" aria-label="Home">
            <Logo class="h-10 w-auto" />
          </a>
          <div class="hidden md:flex md:gap-x-6">
            <NavLink href="#features">Features</NavLink>
            <NavLink href="#testimonials">Testimonials</NavLink>
            <NavLink href="#pricing">Pricing</NavLink>
          </div>
        </div>
        <div class="flex items-center gap-x-5 md:gap-x-8">
          <Button color="blue">
            <span>
              Get started <span class="hidden lg:inline">today</span>
            </span>
          </Button>
          <div class="-mr-1 md:hidden">
            <!-- Mobile Navigation -->
            <button
              @click="mobileMenuOpen = !mobileMenuOpen"
              class="relative z-10 flex h-8 w-8 items-center justify-center focus:outline-hidden"
              aria-label="Toggle Navigation"
            >
              <svg
                aria-hidden="true"
                class="h-3.5 w-3.5 overflow-visible stroke-slate-700"
                fill="none"
                stroke-width="2"
                stroke-linecap="round"
              >
                <path
                  d="M0 1H14M0 7H14M0 13H14"
                  :class="[
                    'origin-center transition',
                    mobileMenuOpen && 'scale-90 opacity-0',
                  ]"
                />
                <path
                  d="M2 2L12 12M12 2L2 12"
                  :class="[
                    'origin-center transition',
                    !mobileMenuOpen && 'scale-90 opacity-0',
                  ]"
                />
              </svg>
            </button>

            <!-- Mobile Menu Backdrop -->
            <transition name="fade">
              <div
                v-if="mobileMenuOpen"
                @click="mobileMenuOpen = false"
                class="fixed inset-0 bg-slate-300/50 duration-150"
              />
            </transition>

            <!-- Mobile Menu Panel -->
            <transition name="scale">
              <div
                v-if="mobileMenuOpen"
                class="absolute inset-x-0 top-full mt-4 origin-top flex flex-col rounded-2xl bg-white p-4 text-lg tracking-tight text-slate-900 shadow-xl ring-1 ring-slate-900/5"
              >
                <a href="#features" class="block w-full p-2" @click="mobileMenuOpen = false">Features</a>
                <a href="#testimonials" class="block w-full p-2" @click="mobileMenuOpen = false">Testimonials</a>
                <a href="#pricing" class="block w-full p-2" @click="mobileMenuOpen = false">Pricing</a>
              </div>
            </transition>
          </div>
        </div>
      </nav>
    </Container>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import Button from './Button.vue'
import Container from './Container.vue'
import Logo from './Logo.vue'
import NavLink from './NavLink.vue'

const mobileMenuOpen = ref(false)
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.15s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.scale-enter-active,
.scale-leave-active {
  transition: transform 0.15s ease-out, opacity 0.15s ease-out;
}

.scale-enter-from,
.scale-leave-to {
  transform: scale(0.95);
  opacity: 0;
}
</style>
