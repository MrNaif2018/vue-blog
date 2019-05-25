<template>
  <div class="details">
    <h1>Post Details</h1>
    <h2>{{post.title}}</h2>
    <h1>Content:</h1>
    <p>{{post.body}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "postdetail",
  data: function() {
    return { post: null };
  },
  mounted: function() {
    axios
      .get(
        "https://jsonplaceholder.typicode.com/posts/" + this.$route.params.post
      )
      .then(response => (this.post = response.data));
  }
};
</script>
