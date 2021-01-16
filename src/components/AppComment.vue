<template>
  <div class="container">
    <p>
      <button v-if="comments.length === 0"  class="btn primary" @click="getComments">Загрузить комментарии</button>
    </p>
    <div class="card" v-if="comments.length !== 0" >
      <h2>Комментарии</h2>
      <ul class="list">
        <li class="list-item" v-for="comment of comments" :key="comment.id">
          <div>
            <p><strong>{{ comment.email }}</strong></p>
            <small>{{ comment.body }}</small>
          </div>
        </li>
      </ul>
    </div>
    <div v-if="isLoading" class="loader"></div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "AppComment",

  data() {
    return {
      comments: [],
      isLoading: false,
    }
  },

  methods: {

    /**
     * Запрос комметариев с сервера
     */
    async getComments() {
      this.isLoading = true
      const response = await axios.get('https://jsonplaceholder.typicode.com/comments?_limit=42')
      try {
        this.comments = response.data
        this.isLoading = false
      } catch (e) {
        this.isLoading = false
        console.warn(e)
      }


    }
  }
}

</script>

<style scoped>

</style>