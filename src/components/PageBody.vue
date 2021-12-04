<template>
    <div>
        <!-- Learned about the v-on in a video, same thing as @click and then we change the page layout
        variable to the opposite of what is is -->
        <button v-on:click="page_layout = !page_layout">Toggle View!</button>
        <!-- If the page_layout variable is true it will render the section with the class row-view -->
        <section v-if="page_layout === true" class="row-view">
            <!-- Looping through the tweets to show them on the page -->
            <tweet-card v-for="tweet in tweets" :key="tweet.tweet_id" :username="tweet.username" :tweet_content="tweet.tweet_content" :date_created="tweet.date_created"></tweet-card>
        </section>
        <!-- If page_layout is false we show the column view and loop through the same way as above -->
        <section v-else class="column_view">
        <tweet-card v-for="tweet in tweets" :key="tweet.tweet_id" :username="tweet.username" :tweet_content="tweet.tweet_content" :date_created="tweet.date_created"></tweet-card>
        </section>
    </div>
</template>

<script>
import TweetCard from './TweetCard.vue'
    export default {
        name: 'page-body',
        components: {
            TweetCard,
        },
        data() {
            return {
                page_layout: true,
                tweets: [
                    {
                        username: "John",
                        tweet_content: "First Tweet Ever!",
                        date_created: "05/05/2021",
                        tweet_id: 1
                    },
                    {
                        username: "Mike",
                        tweet_content: "Second Tweet Ever!",
                        date_created: "05/07/2021",
                        tweet_id: 2
                    },
                    {
                        username: "Tim",
                        tweet_content: "Third Tweet Ever!",
                        date_created: "05/11/2021",
                        tweet_id: 3
                    },
                    {
                        username: "Bill",
                        tweet_content: "Fourth Tweet Ever!",
                        date_created: "05/13/2021",
                        tweet_id: 4
                    },
                    {
                        username: "Bobby",
                        tweet_content: "Fifth Tweet Ever!",
                        date_created: "05/16/2021",
                        tweet_id: 5
                    },
                    {
                        username: "Lucky",
                        tweet_content: "Sixth Tweet Ever!",
                        date_created: "05/05/2021",
                        tweet_id: 6
                    },
                ]
            }
        },
    }
</script>

<style scoped>
    .row_view {
        display: grid;
        place-items: center
    }

        .column_view {
        display: grid;
        grid-auto-flow: column;
    }
</style>