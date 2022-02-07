<template>
  <div>
    <CommentForm @addComment="createComment"/>
    <CommentList :comments="comments"/>
  </div>
</template>

<script>
import CommentForm from "@/components/CommentForm";
import CommentList from "@/components/CommentList";

export default {
  name: 'HelloWorld',
  components: {
    // eslint-disable-next-line vue/no-unused-components
    CommentForm,
    // eslint-disable-next-line vue/no-unused-components
    CommentList,
  },
  data() {
    return {
      comments: [
        {id: 1, name: 'Ozod', email: 'ozodjon6@gmail.com', content: 'bir nimalar'},
        {id: 2, name: 'Javoxir', email: 'jaavoxir@gmail.com', content: 'xazilni birimi'},
        {id: 3, name: 'Dilsho', email: 'dilshod1@gmail.com', content: 'Bratan gap yoq'}
      ],
    }
  },
  methods: {
    createComment(comment) {
      this.comments.push(comment)
    }
  }


}
</script>

<style scoped>

</style>
