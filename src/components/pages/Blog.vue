<template>
  <Section>
    <template v-slot:title> Our Latest News </template>

    <template v-slot:body>
      There are many variations of passages of Lorem Ipsum available, but the
      majority have suffered alteration, by injected humour, or new randomised
      words.
    </template>

    <!-- <slot name="body">
      There are many variations of passages of Lorem Ipsum available, but the
      majority have suffered alteration, by injected humour, or new randomised
      words.
    </slot> -->

    <div class="max-w-lg mx-auto grid gap-5 lg:grid-cols-3 lg:max-w-none">
      <div
        v-for="post in posts"
        :key="post.title"
        class="flex flex-col rounded-lg shadow-lg overflow-hidden"
      >
        <div class="flex-shrink-0">
          <img class="h-48 w-full object-cover" :src="post.imageUrl" alt="" />
        </div>
        <div class="flex-1 bg-white p-6 flex flex-col justify-between">
          <div class="flex-1">
            <p class="text-sm font-medium text-indigo-600">
              <a :href="post.category.href" class="hover:underline">
                {{ post.category.name }}
              </a>
            </p>
            <a :href="post.href" class="block mt-2">
              <p class="text-xl font-semibold text-gray-900">
                {{ post.title }}
              </p>
              <p class="mt-3 text-base text-gray-500">
                {{ post.description }}
              </p>
            </a>
          </div>
          <div class="mt-6 flex items-center">
            <Button> Read More </Button>
          </div>
        </div>
      </div>
    </div>
  </Section>
</template>

<script>
import Button from "../Button.vue";
import Section from "../layout/Section.vue";

export default {
  components: {
    Button,
    Section,
  },

  data() {
    return {
      posts: [],
    };
  },

  created() {
    fetch("http://localhost:3001/blog")
      .then((res) => res.json())
      .then((data) => {
        this.posts = data;
      })
      .catch((err) => console.log(err));
  },
};
</script>
