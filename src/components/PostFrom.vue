<template>
  <form @submit.prevent>
    <h4>Create a post</h4>
    <CustomInput
        v-model="post.title"
        type="text"
        placeholder="Post Title"
    />
    <CustomInput
        v-model="post.body"
        type="text"
        placeholder="Post Body"
    />
    <CustomButton
        class="btn"
        style="align-self: flex-end; margin-top: 15px;"
        @click="createPost"
    >
      Create
    </CustomButton>
  </form>
</template>

<script>

export default {
  data() {
    return {
      post: {
        id: null,
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post);

      this.post = {
        id: null,
        title: '',
        body: '',
      }
    }
  }
}
</script>

<style lang="scss" scoped>

</style>
