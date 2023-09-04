<script setup>
const { data: posts } = await useAsyncData('posts', () =>
  queryContent('/blog').find()
)
</script>

<template>
  <div class="mx-auto max-w-7xl px-2 sm:px-6 lg:px-8 mt-8">
  <h1 class="rounded-lg shadow-lg font-bold text-4xl my-8 bg-sky-700 px-1 py-2 text-center text-yellow-400">Blog Posts</h1>

  <p class="bg-sky-700 text-yellow-200 rounded-lg shadow-lg p-6 mt-6">
  I like to write about anything thta I am currently working or something new that interests me. If you would like me to
  write about something or be a guest blogger on your blog please reach out to me on Twitter. If you would like to
  subscribe to an RSS feed you can find it here.
</p>
  <section class="grid md:grid-cols-3 my-8 gap-10">
    <Post :posts="posts" />
  </section>
</div>
</template>