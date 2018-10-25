<template>
  <div class="schedule">
    <h1 class="is-size-1">{{post.title.rendered}}</h1>
    <div class="content" v-html="post.content.rendered"></div>
  </div>
</template>

<script>
  import axios from 'axios'
  export default {
    data: function() {
      return {
        post: undefined
      }
    },
    created() {
      axios.get('https://2018.johannesburg.wordcamp.org/wp-json/wp/v2/pages/7')
        .then(response => {
          this.post = response.data
        })
    }
  }
</script>
