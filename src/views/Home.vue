<template>
  <v-card>
    <v-card-title>Recent Books People Have Looked For</v-card-title>
    <v-card-text>
      <v-row>
        <v-col v-for="book in books" :key="book.title" cols="6">
          <v-card>
            <v-card-title>{{book.title}}</v-card-title>
            <v-card-text>
              <v-img contain height="100px" width="150px" src="@/assets/book.jpg"></v-img>
              {{book.description}}
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      books: [
        {
          title: "Book 1",
          description: "This is the book ones description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
        {
          title: "Book 2",
          description: "This is the book twos description",
          cover: "book.jpg",
        },
      ],
    };
  },
};
</script>
