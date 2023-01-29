<script setup lang="ts">
const route = useRoute();
const { id } = route.query;
const { article, fetchArticle } = useArticles();
if (id) {
	fetchArticle(+id);
}
</script>

<template>
  <div>
    <div class="container">
      <article v-if="article">
        <p>タイトル：{{ article.title }}</p>
        <hr />
        <div style="width: 500px">{{ article.content }}</div>
      </article>
      <NuxtLink to="/">戻る</NuxtLink>
    </div>
    <Advertisement />
  </div>
</template>

<style scoped>
header {
  border-bottom-style: solid;
  padding: 1rem;
}
footer {
  margin-top: 2rem;
  background-color: #8080ee;
  padding: 1rem;
}
.container {
  margin: 2rem;
}
</style>
