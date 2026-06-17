<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Create a post</h4>
      <input
          v-bind:value="title"
          @input="title = $event.target.value"
          class="input"
          type="text"
          placeholder="Post Title"
      >
      <input
          v-bind:value="body"
          @input="body = $event.target.value"
          class="input"
          type="text"
          placeholder="Post Body"
      >
      <button class="btn" @click="createPost">Create</button>
    </form>
    <div class="post" v-for="post in posts">
      <div><strong>Title: </strong> {{ post.title }}</div>
      <div><strong>Body: </strong> {{ post.body }}</div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        posts: [
          {
            id: 1,
            title: 'Javascript',
            body: "JS is a programming language",
          },
          {
            id: 2,
            title: 'CSS',
            body: "CSS is a style language",
          },
          {
            id: 3,
            title: 'HTML',
            body: "HTML is a markup language",
          }
        ],
        title: '',
        body: '',
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
        this.title = "";
        this.body = "";
      },
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  .app {
    padding: 20px;
  }

  form {
    display: flex;
    flex-direction: column;
  }

  .post {
    padding: 20px;
    border: 2px solid teal;
    margin-top: 15px;
  }

  .input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 20px;
  }

  .btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    border: 1px solid teal;
  }
</style>
