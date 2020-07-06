<template>
    <div>
        <h1>{{ title }}</h1>
        <ul>
            <book-item 
                 v-for='book in books'
                  :key='book.id' 
                  :book='book'
                  ></book-item>
        </ul>
        <book-form @addBook='appendBook'></book-form>
    </div>
</template>

<script>
    import BookItem from './BookItem';
    import BookForm from './BookForm';
    
    export default {
        components : { BookItem, BookForm },
        name: 'BookList',
        methods: {
            appendBook(bookTitle, bookAuthor) {
                this.books.push({ title: bookTitle, author: bookAuthor });
            },
        },
        data() {
          return { 
                title: 'All Books',
                books:[
                            {title: 'The 7 Habits of Highly Successful People', author: 'Stephen R. Covey'},
                            {title: 'How to Win Friends and Influence People', author: 'Dale Carnegie'},
                            {title: 'The Power of Now: A Guide To Spiritual Enlightenment', author: 'Eckhart Tolle'},
                            {title: 'Think and Grow Rich', author: 'Napoleon Hill'},
                      ]
              };
        }    
    };
</script>

<style  scoped>
    h1, h2 {
      font-weight: normal; 
    }
    ul {
        list-style-type: none;
        padding: 0;
    }


</style>