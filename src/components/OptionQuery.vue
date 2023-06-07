<template>
<h1>Comments</h1>
<div v-if="$apollo.queries.comments.loading">
    <h3>Loading...</h3>
</div>
<ul v-else>
    <li v-for="comment,index in comments" :key="index">
    <b>{{ comment.name }}</b>: {{ comment.text }}
    </li>
</ul>
</template>

<script lang='ts'>
import { defineComponent } from 'vue';
import gql from 'graphql-tag';

export default defineComponent({
    name: "App",
    apollo: {
    comments : {
        query: gql`
        query($name: String!) {
        comments: getCommentsFromUser(name: $name) {
            text
        }
        }
        `,
        variables(){
        return {
            name: 'User 1'
        }
        },
        fetchPolicy: 'cache-and-network'
    }
    },
    data(){
    return {
        comments : []
    }
    }
})
</script>

<style scoped>

</style>