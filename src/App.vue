<template>
  <div class="container">
    <div class="row">
      <SearchBook v-on:search-input="searchString" />
      <div v-for="book in filteredBooks" :key="book.id" class="col-md-12">
        <Book 
          :title="book.title" :image="book.image"/>
      </div>
    </div>    
  </div>
</template>

<script>
import SearchBook from './components/SearchBook.vue'
import Book from './components/Book.vue'

export default {
  components: { Book, SearchBook },
  data() {
    return {
      books: [
        { id: 1, title:  'Everything You Need About CSS', image: 'css_books.jpg' },
        { id: 2, title:  'Creating Beautiful Web with Javascript', image: 'javascript_books.jpg' },
        { id: 3, title:  'Administering Linux System Server Fundamental', image: 'linux_books.jpg' },
        { id: 4, title:  'Creating ecommerce web with VUE JS', image: 'vuejs_books.jpg' },
        { id: 5, title:  'Become Windows System Administrator', image: 'windows_books.jpg' },
      ],
      searchSTring: '',
      filteredBooks: [],
    }
  },
  mounted() {
    this.filteredBooks = this.books;
  },
  methods: {
    searchString(searchInput) 
      { 
        if (searchInput.trim() === '') {
          console.log('search')
          this.filteredBooks = this.books;
        }

        this.filteredBooks = this.books.filter(book => {
          return book.title.toLowerCase().includes(searchInput.toLowerCase())
        })
      }
  }

}
</script>

<style scoped>

</style>
