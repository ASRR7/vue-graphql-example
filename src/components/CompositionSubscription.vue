<template>
<h1>Comments</h1>
<ul>
    <li v-for="comment,index in comments" :key="index">
    <b>{{ comment.name }}</b>: {{ comment.text }}
    </li>
</ul>
</template>

<script lang='ts'>
import { defineComponent, watch, ref } from 'vue';
import { useSubscription } from '@vue/apollo-composable';
import gql from 'graphql-tag';

export default defineComponent({
    setup(){
    const comments  = ref([]);
    const { result } = useSubscription(gql`
    subscription Subscription {
        commentCreated {
        name,
        text
        }
    }
    `)

    watch(
        result,
        data => {
        comments.value.push(data.commentCreated)
        console.log("New comment recive!" + data.commentCreated);
        }
    )
    return {
        comments
    }
    }
})
</script>

<style scoped>

</style>