<script setup>
import Section from "../layout/Section.vue";
import Button from "../Button.vue";
import SecondaryButton from "../SecondaryButton.vue";
import Card from "../layout/Card.vue";
</script>
<template>
  <Section>
    <template v-slot:title> Great Pricing Plans </template>

    <template v-slot:body>
      There are many variations of passages of Lorem Ipsum available, but the
      majority have suffered alteration, by injected humour, or new randomised
      words.
    </template>

    <div class="grid grid-cols-1 sm:grid-cols-1 md:grid-cols-3 gap-4">
      <Card
        title="STANDARD"
        price="$19"
        billing="Per Month"
        :features="['24/7 Support', '50 Gb Bandwidth', '10 PremiumThemes ']"
      />

      <Card
        title="SILVER"
        price="$29"
        billing="Per Month"
        :features="[
          '24/7 Support',
          '200 Gb Bandwidth',
          'Unlimited Experiences',
        ]"
        color="bg-gray-300"
      />

      <Card
        title="GOLD"
        price="$99"
        billing="Per Month"
        :features="['24/7 Support', 'Unlimited Bandwidth', 'All Experiences']"
        color="bg-gradient-to-r from-purple-500 via-blue-500 to-blue-600 text-white group hover:bg-gradient-to-r hover:m-purple-400 hover:via-blue-400 hover:to-blue-500 transition duration-300"
      />

      <!-- <div class="p-4">
        <div
          class="bg-gradient-to-r from-purple-500 via-blue-500 to-blue-600 shadow-lg rounded-lg overflow-hidden group hover:bg-gradient-to-r hover:m-purple-400 hover:via-blue-400 hover:to-blue-500 transition duration-300"
        >
          <div class="px-6 py-8 text-white">
            <h3 class="text-2xl font-semibold">GOLD</h3>
            <p class="text-4xl font-bold mt-2">$99</p>
            <p class="text-gray-300">Per Month</p>
            <Button> Get Started </Button>
          </div>
          <div class="px-6 py-4 border-t border-gray-200">
            <ul class="text-gray-300">
              <li class="mb-2">24/7 Support</li>
              <li class="mb-2">Unlimited Bandwidth</li>
              <li class="mb-2">All Experiences</li>
            </ul>
          </div>
        </div>
      </div> -->
    </div>
  </Section>
</template>
