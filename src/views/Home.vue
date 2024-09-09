<template>
  <div class="home">
    <h1>Home</h1>
    <PostList v-if="showPosts"  :posts="posts" />
    <button @click="showPosts = !showPosts">toggle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import { ref } from 'vue';

export default {
  name: 'Home',
  components: { PostList },
  setup() {
    const posts = ref([
      {title: 'welcome to the blog', body: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse nibh libero, facilisis eget convallis vitae, viverra et diam. Quisque commodo nisi non quam commodo, sed euismod mi feugiat. Nulla in consectetur dolor. Aliquam porta et magna eu consectetur. Praesent vitae efficitur quam. Suspendisse a ornare lacus. Praesent purus velit, sollicitudin sed consequat eget, porttitor id nisi. Phasellus gravida tellus mauris, sit amet pretium sem convallis eu.', id: 1},
      {title: 'top 5 css tips', body: 'lorem ipsum', id: 2},
    ])
    const showPosts = ref(true)

    return { posts, showPosts }
  }
}
</script>
