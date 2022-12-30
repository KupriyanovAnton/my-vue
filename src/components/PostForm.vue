<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <my-input
        v-model="post.title"
        placeholder="Название"
    />
    <my-input
        v-model="post.body"
        placeholder="Описание"
    />
    <my-button @click="createPost" style="align-self: flex-end; margin-top: 15px">Создание</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now()
      this.$emit('create', this.post);
      this.post = {
        title: '',
        body: '',
      }
    },
    asd(event) {
      this.post.title = event.target.value;
    },
    qwe(event) {
      this.post.body = event.target.value;
    }
  }
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
</style>