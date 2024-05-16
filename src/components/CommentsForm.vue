<template>
  <form @submit.prevent>
      <h4>Добавьте свой комментарий</h4>
      <input 
        v-model="comment.name"
        class="input" 
        type="text" 
        placeholder="Ваше Имя"
      >
      <input 
        v-model="comment.body"
        class="input" 
        type="text" 
        placeholder="Ваш Комментарий"
      >
      <button 
        class="btn"
        @click="createComment"
      >
        Добавить
      </button>
    </form>
</template>

<script>
export default {
  data() {
    return {
      comment: {
        name: '',
        body: '',
      }
    }
  },

  methods: {
    createComment() {
      this.comment.id = Date.now();
      this.$emit('create', this.comment)
      this.comment = {
        name: '',
        body: ''
      }
    }
  }
}
</script>

<style>
form {
  display: flex;
  flex-direction: column;
}

.input {
  width: 100%;
  border: 2px solid DarkSlateGray;
  padding: 10px 15px;
  margin-top: 15px;
  border-radius: 40px;
}

.btn {
  align-self: center;
  margin-top: 15px;
  padding: 10px 15px;
  border-radius: 40px;
  border: 2px solid DarkSlateGray;
}
</style>