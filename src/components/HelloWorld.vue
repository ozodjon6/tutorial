<template>
  <div>
    <Navbar :showModal="showModal"/>
    <my-modal :show="modalVisible">
      <CommentForm @addComment="createComment"/>
    </my-modal>
    <CommentList :comments="comments" @remove="removeComment"/>
  </div>
</template>

<script>
import CommentForm from "@/components/CommentForm";
import CommentList from "@/components/CommentList";
import Navbar from "@/components/Navbar";
import MyModal from "@/components/UI/MyModal";

export default {
  name: 'HelloWorld',
  components: {
    MyModal,
    CommentForm,
    CommentList,
    // eslint-disable-next-line vue/no-unused-components
    Navbar,
  },
  data() {
    return {
      comments: [
        {id: 1, name: 'Ozod', email: 'ozodjon6@gmail.com', content: 'bir nimalar'},
        {id: 2, name: 'Javoxir', email: 'jaavoxir@gmail.com', content: 'xazilni birimi'},
        {id: 3, name: 'Dilsho', email: 'dilshod1@gmail.com', content: 'Bratan gap yoq'}
      ],
      modalVisible: false
    }
  },
  methods: {
    createComment(comment) {
      this.comments.push(comment);
      this.modalVisible = false;
    },
    removeComment(comment) {
      this.comments = this.comments.filter(c => c.id !== comment.id)
    },
    showModal() {
      this.modalVisible = true
    }
  }


}
</script>

<style scoped>

</style>
