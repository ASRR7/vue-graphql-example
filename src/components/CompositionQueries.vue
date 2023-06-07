<template>
<h1>Comments</h1>
<!-- <div v-if="loading"><h3>Loading...</h3></div>
<div v-else>
    <ul>
    <li class="comment-list-li" v-for="comment, index in result.getCommentsFromUser" :key="index">
        <b>{{ comment.name }}</b>: {{ comment.text }}
    </li>
    </ul>
</div>

<button @click.prevent="refetch">Refresh</button>

<div v-if="error"><h3 class="error">Error: {{ error.message }}</h3></div> -->

</template>

<script lang='ts'>
// import { ref, defineComponent } from 'vue';
// import { useQuery, useMutation } from '@vue/apollo-composable';
// import gql from 'graphql-tag';

// export default defineComponent({
//     setup(){
//     // const {result, loading, error} = useQuery(gql`
//     //   query {
//     //-->  getAllComments {
//     //       name
//     //       text
//     //     }
//     //   }
//     // `)

//     // const {result, loading, error, refetch, onResult, onError} = useQuery(gql`
//     //   query($name: String!) {
//     //     getCommentsFromUser(name: $name) {
//     //       name,
//     //       text
//     //     }
//     //   }
//     // `,() => ({
//     //   name: "User 1"
//     // }), {
//     //   fetchPolicy : "cache-and-network",
//     //   pollInterval : 5000,

//     // })
        
//         // onResult((queryResult)=>{
//         //   console.log(queryResult.data, queryResult.loading, queryResult.networkStatus);
//         // })
//         // onError((queryError)=>{
//         //   console.error(queryError.graphQLErrors);
//         // })

//         const {mutate: createComment, loading: createCommentLoading, error: createCommentError, onDone, onError  } = useMutation(gql`
//             mutation Mutation($name: String!, $text: String!) {
//             createComment(name: $name, text: $text)
//             }
//         `,() => ({
//             variables : {
//             name: "Pepillo",
//             text: "Helloadsad"
//             },
//             update : (cache, {data: {createComment}}) => {
//             let data = cache.readQuery({query: getAllComments}),
//             data = {
//                 ...data,
//                 comments : {
//                 ...data.comment,
//                 createComment
//                 }
//             }

//             cache.readQuery({query: getAllComments}, data )
//             }
//         }))

//         onDone((done) => {
//         console.log(done.value);
//         })
//         onError((error) => {
//         console.error(error.message);
//         })
//     return {
//         createComment
//     }
//     }
// })
</script>

<style scoped>
.error {
    color: red;
}
.comment-list-li {
    margin-bottom: 15px;
}
</style>