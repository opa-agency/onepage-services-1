<template>
  <div class="h-full scroll-smooth bg-white antialiased" style="--font-inter: 'Inter'; --font-lexend: 'Lexend'">
    <div class="flex h-full flex-col">
      <Header />
      <main>
        <Hero />
        <PrimaryFeatures />
        <SecondaryFeatures />
        <CallToAction />
        <Testimonials />
        <Pricing />
        <Faqs />
      </main>
      <Footer />
    </div>
  </div>
</template>

<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import PrimaryFeatures from './components/PrimaryFeatures.vue'
import SecondaryFeatures from './components/SecondaryFeatures.vue'
import CallToAction from './components/CallToAction.vue'
import Testimonials from './components/Testimonials.vue'
import Pricing from './components/Pricing.vue'
import Faqs from './components/Faqs.vue'
import Footer from './components/Footer.vue'
</script>
