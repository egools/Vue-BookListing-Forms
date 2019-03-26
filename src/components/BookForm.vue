<template>
  <form @submit.prevent="bookSubmit(bookData)" class action="#" method="post">
    <input v-model="bookData.bookTitle" type="text" name="title" value placeholder="Book Title">
    <input v-model="bookData.bookAuthor" type="text" name="author" value placeholder="Book Author">
    <div>
      <label for="finishedReading">Finished Reading</label>
      <input
        type="checkbox"
        name="finishedReading"
        id="finishedReading"
        v-model="bookData.finishedReading"
      >
    </div>
    <div>
      <label for="borrowed">Borrowed</label>
      <input
        type="radio"
        name="ownership"
        id="borrowed"
        value="borrowed"
        v-model="bookData.ownership"
      >
      <label for="bought">Bought</label>
      <input
        type="radio"
        name="ownership"
        id="bought"
        value="bought"
        v-model="bookData.ownership"
      >
    </div>
    <button type="submit" name="button">Add Book</button>
  </form>
</template>

<script>
export default {
  name: "BookForm",
  props: ["books"],
  data() {
    return {
      bookData: {
        bookTitle: "",
        bookAuthor: "",
        finishedReading: false,
        ownership: []
      }
    };
  },
  methods: {
    bookSubmit(bookData) {
      this.$emit("addBook", bookData);
    }
  }
};
</script>

<style>
</style>
