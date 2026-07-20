<template>
  <div class="app">
    <PostForm @create="createPost" />
    <PostList
        :posts="posts"
        @remove="removePost"
    />
  </div>
</template>

<script>
  import PostForm from "./components/PostFrom.vue";
  import PostList from "./components/PostList.vue";

  export default {
    components: {
      PostForm, PostList
    },
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
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post);
      },
      removePost(post) {
        this.posts = this.posts.filter(p => p.id !== post.id)
      }
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
</style>
