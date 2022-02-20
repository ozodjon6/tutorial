<template>
  <div>
    <Navbar :showModal="showModal"/>
    <my-modal :show="modalVisible">
      <CommentForm @addComment="createComment"/>
    </my-modal>
    <CommentList :comments="comments" @remove="removeComment" v-if="!isLoading"/>
    <div class="d-flex justify-content-center" v-else>
      <div class="spinner-border" role="status">
        <span class="visually-hidden">Загрузка...</span>
      </div>
    </div>
  </div>
</template>

<script>
import CommentForm from "@/components/CommentForm";
import CommentList from "@/components/CommentList";
import Navbar from "@/components/Navbar";
import MyModal from "@/components/UI/MyModal";
import axios from "axios"

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
      comments: [],
      modalVisible: false,
      isLoading: false,
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
    },
    async fetchComments() {
      try {
        this.isLoading = true
        const response = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=10');
        this.comments = response.data
        console.log(response.data)
        this.isLoading = false
      }catch (e) {
        console.log(e)
      }finally {
        this.isLoading = false
      }
    }
  },
  mounted() {
    this.fetchComments()
  }


}
</script>

<style scoped>

</style>
