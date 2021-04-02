<template>
    <div class="parentContainer" v-if="!$fetchState.pending">
        <input v-model="userInput" placeholder="Search Posts" class="input"/>
        <Post v-for="post in filteredPosts.slice(0,5)" :key="post.id" :post="post" />
        <MyPosts />
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
            wishlist: [],
            boughtItems: [],
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
    .parentContainer {
        display: flex;
        flex-direction: column;
        padding-left: 5rem;
        padding-right: 5rem;
    }
    .input {
        margin-top: 2rem;
        padding: 0.5rem 0.5rem;
        width: 35%;
    }
</style>
