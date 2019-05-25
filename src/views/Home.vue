<template>
  <div class="home">
    <ul>
      <div v-for="post in posts">
        <a :href="'/posts/'+post.id">{{post.title}}</a>
        <p>{{post.body}}</p>
      </div>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "home",
  data: function() {
    return { posts: null };
  },
  mounted: function() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then(response => (this.posts = response.data));
  }
};
</script>
