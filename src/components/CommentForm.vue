<template>
  <div class="hello">
    <form action="#" @submit.prevent>
      <div class="col-sm-5" style="margin: 0 auto">
        <input
            v-model="comment.name"
            type="text"
            required
            class="form-control"
            placeholder="Name">
      </div>
      <div class="col-sm-5" style="margin: 0 auto">
        <input
            v-model="comment.email"
            type="email"
            required
            class="form-control" style="margin: 10px 0;" placeholder="E-mail">
      </div>
      <div class="col-sm-5" style="margin: 0 auto">
        <input
            v-model="comment.content"
            type="text"
            required
            class="form-control" placeholder="Content">
      </div>
      <button @click="createComment" class="btn btn-success" style="margin-top: 12px">Add</button>
    </form>

  </div>
</template>

<script>
export default {
  name: "CommentForm",
  data() {
   return {
     comment: {
       name: '',
       email: '',
       content: ''
     }
    }
  },
  methods: {
    createComment() {
      this.comment.id = Date.now();
      this.$emit('addComment', this.comment);
      this.comment = {
        name: '',
        email: '',
        content: ''
      }
    }
  }
}
</script>

<style scoped>

</style>