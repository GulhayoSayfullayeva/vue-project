<template>
    <div v-if="booklist">
        <div v-for="book in booklist" :key="book.id">
            <Book :book="book" />
        </div>

    </div>
    <div v-else>
        <h1>Loading....</h1>
    </div>

</template>

<script>

import Book from './Book.vue'

export default {
    components: { Book },

    data() {
        return {
            booklist: []
        }
    },
    mounted() {
        fetch('http://localhost:3000/docs')
            .then(response => response.json())
            .then((data) => {
                this.booklist = data
                console.log(this.booklist)
            })
            .catch((error) => console.log(error.message))
    }
}
</script>

<style></style>