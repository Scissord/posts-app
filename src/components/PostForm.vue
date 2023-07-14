<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <my-input
        class="btn__title"
        v-focus
        v-model="post.title"
        type="text"
        placeholder="Название"
    />
    <my-input
        class="btn__body"
        v-model="post.body"
        type="text"
        placeholder="Создать"
    />
    <my-button
        class="btn"
        @click="createPost"
        style="margin-top: 15px"
    >
      Создать
    </my-button>
  </form>
</template>

<script>

export default {
  data() {
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
        body: '',
      }
    }
  }
}
</script>

<style scoped>
.btn__title {
  width: 100%;
}
.btn__body {
  width: 100%;
}
</style>