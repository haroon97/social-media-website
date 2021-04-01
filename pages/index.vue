<template>
  <div class="container" v-if="!$fetchState.pending">
      <input v-model="userInput" placeholder="Search Posts" class="input"/>
      <Post v-for="post in filteredPosts" :key="post.id" :post="post" />
  </div>
  <div v-else>
      Loading...
  </div>

</template>

<script>
export default {
    data() {
        return {
            posts: [],
            userInput: '',
        }
    },
    computed: {
        filteredPosts() {
            return this.posts.filter((post) => {
                return post.title.toLowerCase().includes(this.userInput.toLowerCase());
            })
        }
    },
    async fetch() {
        this.posts = await fetch(
            'https://jsonplaceholder.typicode.com/posts'
        ).then(res => res.json())
    }

}
</script>

<style scoped>
    .input {
        width: 100%;
    }
</style>
