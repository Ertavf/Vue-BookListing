<template>
  <div>
    <h1>{{title}}</h1>
    <ul>
      <Book-Item v-for="(book, index) in books" :book="book" :key="index"></Book-Item>
    </ul>
    <hr>
    <Book-Form @addBook="appendBook"></Book-Form>
  </div>
</template>

<script>
import BookItem from "./BookItem";
import BookForm from "./BookForm.vue";

export default {
  name: "BookList",
  components: {
    BookItem,
    BookForm
  },
  data() {
    return {
      title: "All Books",
      books: [
        { title: "Self-Reliance", author: "Ralph Waldo Emerson" },
        { title: "American Gods", author: "Neil Gaiman" },
        { title: "Amusing Ourselves to Death", author: "Neil Postman" }
      ]
    };
  },
  methods: {
    appendBook(bookTitle, bookAuthor) {
      this.books.push({ title: bookTitle, author: bookAuthor });
    }
  }
};
</script>

<style>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
</style>
