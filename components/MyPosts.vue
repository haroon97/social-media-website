<template>
    <div class="row">
        <div class="col-12">
            <h4 class="text">{{ title }}</h4>
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">#</th>
                        <th scope="col">Title</th>
                        <th scope="col">Body</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="item in posts" :key="item.id" >
                    <th scope="row">{{ item.id }}</th>
                    <td>{{ item.title }}</td>
                    <td>{{ item.body }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>

</template>

<script>
    export default {
        props: ['posts', 'title'],
    }
</script>

<style scoped>
    .row {
        padding-top: 2rem;
    }
    .text {
        text-align: center;
    }
</style>