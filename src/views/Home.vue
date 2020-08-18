<template>
<div>
  <v-card>
    <v-card-title>Home</v-card-title>
      <v-list>
        <v-list-item
          v-for="book in books"
          :key="book.title"
        >
          <v-list-item-content>
            <v-list-item-title>{{ book.title }}</v-list-item-title>
            <v-list-item-content>{{ book.description }}</v-list-item-content>
          </v-list-item-content>
        </v-list-item>
      </v-list>
  </v-card>
</div>
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      books: [
        { title: 'Book 1', description: 'This is the book ones description'},
        { title: 'Book 2', description: 'This is the book twos description' },
        { title: 'Book 1', description: 'This is the book ones description'},
        { title: 'Book 2', description: 'This is the book twos description' },
        { title: 'Book 1', description: 'This is the book ones description'},
        { title: 'Book 2', description: 'This is the book twos description' },
        { title: 'Book 1', description: 'This is the book ones description'},
        { title: 'Book 2', description: 'This is the book twos description' },
        { title: 'Book 1', description: 'This is the book ones description'},
        { title: 'Book 2', description: 'This is the book twos description' },

      ],
    }
  }
}
</script>
