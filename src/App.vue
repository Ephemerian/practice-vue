<template>
    <div class="app">
        <post-form
        @create="createPost"
        />
        <post-list 
        :posts="posts"/>
        <!-- <div>
            <div>Количество лайков: <strong>{{ likes }}</strong></div>
            <div>Количество дизлайков: <strong>{{ dislikes }}</strong></div>
        </div>
        <div>
            <button @click="addLike">Like</button>
            <button @click="addDislike">Dislike</button>
        </div> -->
    </div>
</template>


<script>
import PostForm from "@/components/PostForm.vue"
import PostList from "@/components/PostList.vue"
    export default {
        components: {
            PostList, PostForm
        },
        data() {
            return {
                posts: [
                    {id: 1, title: 'T-shirt', body: 'A simple piece of clothing, usually with short sleeves and no collar, that covers the top part of the body'},
                    {id: 1, title: 'Sweater', body: 'A piece of clothing, typically with long sleeves and made from wool, that is worn on the upper part of the body'},
                    {id: 1, title: 'Coat', body: 'An outer piece of clothing with sleeves that is worn over other clothes, usually for warmth'},
                ],
            }
        },
        methods: {
            createPost(post) {
                this.posts.push(post);
            },
        }
    }
</script>


<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.app {
    padding: 20px;
}

.title {
    font-size: 30px;
}

</style>