<script lang="ts">
export {};
</script>

<script setup lang="ts">
const route = useRoute();
const { id } = route.params;
const { data: article } = await useFetch(`/api/blogs/${id}`);
</script>

<template>
  <div>
    <article v-if="article">
      <p>タイトル：{{ article.title }}</p>
      <hr />
      <div style="width: 500px">{{ article.content }}</div>
    </article>
    <NuxtLink to="/">戻る</NuxtLink>
    <Advertisement />
  </div>
</template>
