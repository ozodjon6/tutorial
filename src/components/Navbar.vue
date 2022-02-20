<template>
  <header class="d-flex flex-wrap justify-content-center py-3 mb-4 border-bottom">
    <a href="/" class="d-flex align-items-center mb-3 mb-md-0 me-md-auto text-dark text-decoration-none">
      <svg class="bi me-2" width="40" height="32"><use xlink:href="#bootstrap"></use></svg>
      <span class="fs-4">Simple header</span>
    </a>
    <ul class="nav nav-pills">
      <button @click="showModal" class="btn btn-primary">Add new comment</button>
    </ul>
  </header>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    showModal: {
      type: Function
    }
  },
  methods: {

  }
}
</script>

<style scoped>

header {
  padding: 0 20px;
}

</style>