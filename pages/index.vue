<script lang="ts">
export {};
</script>

<script setup lang="ts">
const { data: articles, refresh } = await useFetch('/api/blogs');
</script>

<template>
  <div>
    <p>新着記事！！</p>
    <ul>
      <li v-for="article in articles" :key="article.id">
        <NuxtLink :to="{path: '/details', query: { id:article.id }}">
          {{article.title}}
        </NuxtLink>
      </li>
    </ul>
    <button @click="() => refresh()">最新情報取得</button>
    <Advertisement />
  </div>
</template>
