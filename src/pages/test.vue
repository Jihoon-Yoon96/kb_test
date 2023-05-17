<template>
    <div>
        <p v-if="isLoading">Loading...</p>
        <p v-else-if="error">Error: {{ error }}</p>
        <ul v-else>
            <li v-for="post in posts" :key="post.id">{{ post.title }}</li>
        </ul>
    </div>
</template>

<script setup lang="ts">
// import { useFetch } from '@nuxtjs/composition-api';

const { data, pending, error, refresh } = await useFetch('http://125.131.88.58:8055/items/notice/',{
    pick: ['title']
})

console.log('data', data)
console.log('pending', pending)
console.log('error', error)
console.log('refresh', refresh)


// export { posts, error, isLoading };
</script>
