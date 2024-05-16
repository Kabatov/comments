<template>
  <div>
    <h3>Список комментариев</h3>
    <CommentsItem 
      v-for="(comment, index) of comments"
      :key="index"
      :comment="comment"
      @remove="$emit('remove', comment)"
    /> 
  </div>
  
</template>

<script>
import CommentsItem from './CommentsItem.vue'

export default {
  components: {
    CommentsItem,
  },
  props: {
      comments: {
          type: Array,
          required: true
      }
  }
}
</script>

<style>

</style>