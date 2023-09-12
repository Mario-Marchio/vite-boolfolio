
<script>
import axios from 'axios';
const endpoint = 'http://127.0.0.1:8000/api/posts/';
export default {
  data: () => ({ posts: [] }),
  methods: {
    fetchPost() {
      axios.get(endpoint).then(res => { console.log(res.data) })
    }
  },
  created() {
    this.fetchPost();
  },
};
</script>

<template>
  <main class="container my-3">
    <ul>
      <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
    </ul>
  </main>
</template>

<style></style>
