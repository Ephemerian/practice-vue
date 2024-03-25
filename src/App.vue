<template>
    <div class="app">
        <form @submit.prevent>
            <h4 class="title">Create new post</h4>
            <input
            v-bind:value="title"
            @input="title = $event.target.value"
            class="input" 
            type="text" 
            placeholder="Name">
            <input
            v-bind:value="body"
            @input="body = $event.target.value"
            class="input" 
            type="text" 
            placeholder="Description">
            <button class="btn" @click="createPost">Create</button>
        </form>
        <div>
            <h4 class="title">Check out our new posts!</h4>
            <div class="post" v-for="post in posts">
                <div><strong>Name: </strong> {{ post.title }} </div>
                <div><strong>Description: </strong> {{ post.body }} </div>
            </div>
        </div>
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
    export default {
        data() {
            return {
                posts: [
                    {id: 1, title: 'T-shirt', body: 'A simple piece of clothing, usually with short sleeves and no collar, that covers the top part of the body'},
                    {id: 1, title: 'Sweater', body: 'A piece of clothing, typically with long sleeves and made from wool, that is worn on the upper part of the body'},
                    {id: 1, title: 'Coat', body: 'An outer piece of clothing with sleeves that is worn over other clothes, usually for warmth'},
                ],
                title: '',
                body: ''
            }
        },
        methods: {
            createPost() {
                const newPost = {
                    id: Date.now(),
                    title: this.title,
                    body: this.body,
                }
                this.posts.push(newPost);
                this.title = '';
                this.body = '';
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

.form {
    display: flex;
    flex-direction: column;
}

.title {
    font-size: 30px;
}

.input {
    width: 100%;
    border: 2px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
    border-radius: 5px;
}

.btn {
    margin-top: 15px;
    margin-bottom: 50px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 2px solid teal;
    border-radius: 5px;
    font-weight: 700;
    transition: all .3s cubic-bezier(.4,0,.2,1);
}
.btn:hover,
.btn:focus {
    transition: all 0.5s;
    color: white;
    background-color: teal;
    border: 2px solid black;
}

.post {
    margin-top: 15px;
    padding: 15px;
    border: 2px solid darkcyan;
    border-radius: 5px;
}

</style>