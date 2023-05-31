<template>
  <section>
    <div class="flex justify-center items-center mt-52">
      <div class="flex items-center justify-between">
        <form @submit.prevent="login" class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
          <div>
            <label for="title" class="text-gray-700 text-sm font-bold mb-2">Email: </label>
            <input type="text" id="email" v-model="postData.user.email">
          </div>
          <div class="flex items-center justify-between">
            <label for="password" class="text-gray-700 text-sm font-bold mb-2">Password: </label>
            <input type="password" id="password" v-model="postData.user.password">
          </div>
          <button class="bg-blue-600 hover:bg-black text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline">
            Sign In
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      postData: {
        user: {
          email:  '',
          password:   ''
        }
      }
    }
  },
  methods: {
    login() {
    axios
      .post('http://localhost:4000/login', this.postData)
      .then((response) => console.log(response))
  }
  }
}
</script>