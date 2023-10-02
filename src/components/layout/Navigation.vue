<script setup>
import {
  Disclosure,
  DisclosureButton,
  DisclosurePanel,
  Menu,
  MenuButton,
  MenuItem,
  MenuItems,
} from "@headlessui/vue";
// import { BellIcon, MenuIcon, XIcon } from '@heroicons/vue/outline'
import SecondaryButton from "../SecondaryButton.vue";

const menuItems = [
  { text: "Home", link: "#" },
  { text: "Work", link: "#" },
  { text: "Blog", link: "#" },
  { text: "Project", link: "#" },
  { text: "Stats", link: "#" },
  { text: "Price", link: "#" },
  { text: "Contact Us", link: "#" },
];
</script>

<template>
  <Disclosure
    as="nav"
    class="bg-white shadow absolute inset-x-0 top-0 z-50"
    v-slot="{ open }"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex justify-between h-16">
        <div class="flex">
          <div class="flex-shrink-0 flex items-center">
            <img
              class="block lg:hidden h-14 w-auto"
              src="https://scontent.fprn4-1.fna.fbcdn.net/v/t39.30808-6/273217099_1634381093579084_7848310056613169894_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=__UtXrjwFVMAX8LONZ-&_nc_ht=scontent.fprn4-1.fna&oh=00_AfC2dfF1pQL0XhnlxyT7ZOnNRE63EaIuS_g04KNu_sb96A&oe=651C36C7"
              alt="Workflow"
            />
            <img
              class="hidden lg:block h-8 w-auto"
              src="https://scontent.fprn4-1.fna.fbcdn.net/v/t39.30808-6/273217099_1634381093579084_7848310056613169894_n.jpg?_nc_cat=106&ccb=1-7&_nc_sid=a2f6c7&_nc_ohc=__UtXrjwFVMAX8LONZ-&_nc_ht=scontent.fprn4-1.fna&oh=00_AfC2dfF1pQL0XhnlxyT7ZOnNRE63EaIuS_g04KNu_sb96A&oe=651C36C7"
              alt="Workflow"
            />
          </div>
          <div class="hidden sm:ml-6 sm:flex sm:space-x-8">
            <a
              v-for="item in menuItems"
              :key="item.text"
              :href="item.link"
              class="border-transparent text-gray-500 hover:border-gray-300 hover:text-gray-700 inline-flex items-center px-1 pt-1 border-b-2 text-sm font-medium"
            >
              {{ item.text }}
            </a>
          </div>
        </div>

        <div class="hidden sm:ml-6 sm:flex sm:items-center">
          <button
            type="button"
            class="bg-white p-1 rounded-full text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
          >
            <SecondaryButton> Get Startet </SecondaryButton>
            <BellIcon class="h-6 w-6" aria-hidden="true" />
          </button>
        </div>
        <div class="-mr-2 flex items-center sm:hidden">
          <!-- Mobile menu button -->
          <DisclosureButton
            class="inline-flex items-center justify-center p-2 rounded-md text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500"
          >
            <span class="sr-only">Open main menu</span>
            <MenuIcon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
            <XIcon v-else class="block h-6 w-6" aria-hidden="true" />
          </DisclosureButton>
        </div>
      </div>
    </div>

    <DisclosurePanel class="sm:hidden">
      <div class="pt-2 pb-3 space-y-1">
        <!-- Current: "bg-indigo-50 border-indigo-500 text-indigo-700", Default: "border-transparent text-gray-500 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-700" -->

        <DisclosureButton
          v-for="item in menuItems"
          :key="item.text"
          :href="item.link"
          as="a"
          class="border-transparent text-gray-500 hover:bg-gray-50 hover:border-gray-300 hover:text-gray-700 block pl-3 pr-4 py-2 border-l-4 text-base font-medium active:bg-indigo-50 active:border-indigo-500 active:text-indigo-700"
        >
        {{ item.text }}
        </DisclosureButton>
      </div>
    </DisclosurePanel>
  </Disclosure>
</template>
