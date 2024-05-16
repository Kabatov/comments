<template>
  <div class="comments">
    <div>
        <div class="user-name">Имя пользователя: <strong>{{ comment.name }}</strong></div>
        <div class="user-text">Комментарий: <strong>{{ comment.body }}</strong></div>
    </div>
    <div class="comments__btns">
        <button
            @click="$emit('remove', comment)" 
            class="comments__delete"
        >
        Удалить
        </button>
    </div>
  </div>
</template>

<script>
export default {
    props: {
        comment: {
            type: Object,
            required: true
        }
    }
}
</script>

<style>
.comments {
  padding: 15px;
  margin-top: 15px;
  width: 700px;
  background-color: DimGray;
  border: 2px solid DarkSlateGray;
  border-radius: 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.user-name {
  color: Beige;
}

.user-text {
  color: Beige;
}

.comments__delete {
    color: Beige;
    background-color: DimGray;
    width: 80px;
    border: 2px solid Beige;
    border-radius: 20px;
    padding: 10px;
}
</style>