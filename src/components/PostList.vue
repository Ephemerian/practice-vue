<template>
    <div>
        <h4 class="title">Check out our new posts!</h4>
        <div class="post" v-for="post in posts">
            <div><strong>Name: </strong> {{ post.title }} </div>
            <div><strong>Description: </strong> {{ post.body }} </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    posts: {
        type: Array,
        required: true
    }
  }
};
</script>

<style scoped>

.post {
    margin-top: 15px;
    padding: 15px;
    border: 2px solid darkcyan;
    border-radius: 5px;
}

</style>