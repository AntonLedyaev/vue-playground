<template>
  <div class="post">
    <div>
      <div><strong>Title: </strong> {{ post.title }}</div>
      <div><strong>Body: </strong> {{ post.body }}</div>
    </div>
    <div class="post__buttons">
      <CustomButton>Delete</CustomButton>
    </div>
  </div>
</template>

<script>

export default {
  props: {
    post: {
      title: {
        type: String,
        required: true
      },
      body: {
        type: String,
        required: true,
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .post {
    padding: 20px;
    border: 2px solid teal;
    margin-top: 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
</style>
