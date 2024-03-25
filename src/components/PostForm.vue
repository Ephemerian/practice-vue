<template>
  <form @submit.prevent>
            <h4 class="title">Create new post</h4>
            <input
            v-model="post.title"
            class="input" 
            type="text" 
            placeholder="Name">
            <input
            v-model="post.body"
            class="input" 
            type="text" 
            placeholder="Description">
            <button class="btn" @click="createPost">Create</button>
    </form>
</template>

<script>
export default {
  data () {
    return {
        post: {
            title: '',
            body: ''
        }
    }
  },
  methods: {
    createPost() {
        this.post.id = Date.now();
        this.$emit('create', this.post)
        this.post = {
            title: '',
            body: ''
        }
    }
  }
}
</script>

<style scoped>

.form {
    display: flex;
    flex-direction: column;
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

</style>