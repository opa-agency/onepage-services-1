<template>
  <section
    id="get-started-today"
    class="relative overflow-hidden bg-blue-600 py-32"
  >
    <img
      class="absolute top-1/2 left-1/2 max-w-none -translate-x-1/2 -translate-y-1/2"
      src="/images/background-call-to-action.jpg"
      alt=""
      loading="lazy"
      onerror="this.style.opacity='0'"
    />
    <Container class="relative">
      <div class="mx-auto max-w-lg text-center">
        <h2 class="font-display text-3xl tracking-tight text-white sm:text-4xl">
          Get started today
        </h2>
        <p class="mt-4 text-lg tracking-tight text-white">
          It's time to take control of your books. Buy our software so you can
          feel like you're doing something productive.
        </p>
        <Button color="white" class="mt-10">
          Get 6 months free
        </Button>
      </div>
    </Container>
  </section>
</template>

<script setup>
import Button from './Button.vue'
import Container from './Container.vue'
</script>
