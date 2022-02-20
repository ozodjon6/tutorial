<template>
  <div>
    <ul class="nav" style="width: 100%;max-width: 768px; margin: 30px auto 0" v-if="comments.length > 0">
      <h2 class="text-center text-primary">Comments</h2>
      <li class="nav-item col-sm-5 d-flex"
          style="width: 100%; text-align: left;padding: 12px;border: 1px solid grey;margin-bottom: 10px;justify-content: space-between;align-items: center"
          v-for="comment in comments" :key="comment.id">
        <div>
          <b>Name:</b> <span>{{comment.name}}</span> <br>
          <b>Email:</b> <a>{{comment.email}}</a> <br>
          <b>Content:</b> <span>{{comment.body}}</span>
        </div>
        <button class="btn btn-danger" @click="$emit('remove', comment)">Delete</button>
      </li>
    </ul>
    <div v-else>
      <h2 class="text-center text-danger">We can not found any comments</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "CommentList",
  props: {
    comments: {
      type: Array,
      required: true
    }
  }

}
</script>

<style scoped>

</style>