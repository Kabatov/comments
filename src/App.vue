<template>
  <div class="app">
    <CommentsForm @create="createComment"/>
    <CommentsUsers 
      :comments="comments"
      @remove="removeComment"
    />
  </div>
</template>

<script>
import CommentsForm from './components/CommentsForm.vue'
import CommentsUsers from './components/CommentsUsers.vue'

export default {
  components: {
    CommentsForm,
    CommentsUsers
  },

  data() {
    return {
      comments: [],
    }
  },

  methods: {
    createComment(comment) {
      this.comments.push(comment);
    },

    removeComment(comment) {
      this.comments = this.comments.filter(c => c.id !== comment.id)
    },

    async getComments() {
      await fetch('https://jsonplaceholder.typicode.com/comments?_limit=10')
        .then(response => response.json())
        .then((response) => this.comments = response)
    }
  },

  created() {
    this.getComments()
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
</style>
