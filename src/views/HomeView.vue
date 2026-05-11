<script setup lang="ts">
import DefaultLayout from '../layouts/DefaultLayout.vue'
import HeroSection from '../components/landing/HeroSection.vue'
import ProblemsSection from '../components/landing/ProblemsSection.vue'
import ServicesSection from '../components/landing/ServicesSection.vue'
import BenefitsSection from '../components/landing/BenefitsSection.vue'
import AboutSection from '../components/landing/AboutSection.vue'
import CallToActionSection from '../components/landing/CallToActionSection.vue'
import FaqSection from '../components/landing/FaqSection.vue'
</script>

<template>
  <DefaultLayout>
    <HeroSection />
    <ProblemsSection />
    <ServicesSection />
    <BenefitsSection />
    <AboutSection />
    <FaqSection />
    <CallToActionSection />
  </DefaultLayout>
</template>
