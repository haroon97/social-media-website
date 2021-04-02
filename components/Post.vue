<template>
    <div class="postContainer">
        <div class="userInfo">
            <img :src="require('@/assets/images/pic.jpg')" class="img"/>
            <div class="nameContainer">
                <h4 class="username">@Haroon97</h4>
                <span class="name">Haroon Ahmed</span>
            </div>
        </div>
        <div class="postBody">
            <span class="time">10 min ago</span>
            <h4 class="title">{{ post.title }}</h4>
            <p class="body">{{ post.body }}</p>
        </div>
        <div class="postInteraction">
            <div>
                <button class="buttons">Like</button>
                <button class="buttons">Comment</button>
                <button class="buttons">Share</button>
            </div>
            <div>
                <button class="btn btn-primary">Add to Wishlist</button>
                <button class="btn btn-success">Buy</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['post']
    }
</script>

<style scoped>
    /* Main Container */
    .postContainer {
        margin-top: 2rem;
        border: 1px solid #D5DBDB;
    }

    /* Styles for user info container */
    .userInfo {
        display: flex;
        background-color: #F8F9F9;
        align-items: center;
        padding: 1rem 2rem;
        border: 1px solid #D5DBDB;
    }
    .nameContainer {
        display: flex;
        flex-direction: column;
        padding-left: 1.5rem;
    }
    .img {
        border-radius: 100rem;
        width: 6%;
    }

    /* Styles for Post body container */
    .postBody {
        padding: 1rem 2rem
    }
    .title {
        color: #3498DB;
        padding-top: 0.5rem;
    }
    .body {
        padding-top: 0.2rem;
    }
    .time {
        color: #99A3A4;
    }

    /* Styles for post interaction  */
    .postInteraction {
        background-color: #F8F9F9;
        border: 1px solid #D5DBDB;
        padding: 1rem 2rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .buttons {
        color: #3498DB;
        background-color: #F8F9F9;
        border-width: 0;
    }
</style>