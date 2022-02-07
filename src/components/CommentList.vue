<template>
  <ul class="nav" style="width: 100%;max-width: 768px; margin: 30px auto 0">
    <li class="nav-item col-sm-5"
        style="width: 100%; text-align: left;padding: 12px;border: 1px solid grey;margin-bottom: 10px"
        v-for="comment in comments" :key="comment.id">
      <b>Name:</b> <span>{{comment.name}}</span> <br>
      <b>Email:</b> <span>{{comment.email}}</span> <br>
      <b>Content:</b> <span>{{comment.content}}</span>
    </li>
  </ul>
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