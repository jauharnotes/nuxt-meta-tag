<script setup lang="ts">
interface Post {
  title: string;
  body: string;
}

const route = useRoute();
const id = route.params.slug as string;

// Ambil data post dari API secara server-side
const { data: post } = await useAsyncData<Post>(`post-${id}`, () =>
  fetch(`https://jsonplaceholder.typicode.com/posts/${id}`).then((res) =>
    res.json()
  )
);

// Atur meta tag dengan SSR menggunakan `useHead`
useHead({
  title: post?.value?.title || "Blog Post",
  meta: [
    {
      name: "description",
      content: post?.value?.body || "Default description",
    },
    { property: "og:title", content: post?.value?.title || "Blog Post" },
    {
      property: "og:description",
      content: post?.value?.body || "Default description",
    },
    { property: "og:url", content: `https://yourwebsite.com/posts/${id}` },
  ],
});
</script>

<template>
  <div v-if="post">
    <h1>{{ post.title }}</h1>
    <p>{{ post.body }}</p>
  </div>
  <div v-else>
    <p>Loading...</p>
  </div>
</template>
