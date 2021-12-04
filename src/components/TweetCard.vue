<template>
            <section class="tweet_card">
            <h1>{{ username }}</h1>
            <p>{{ tweet_content }}</p>
            <p>{{ date_created }}</p>
            </section>
</template>

<script>
    export default {
        name: 'tweet-card',
        props: {
                username: String,
                tweet_content: String,
                date_created: String,
        
        },
    }
</script>

<style scoped>
    .tweet_card {
        border: 1px solid black;
    }
</style>