<template>
  <form @submit.prevent="submit">
    <div>
      <label for="userId">ID: </label>
      <input id="userId" type="text" v-model="userId">
    </div>
    <div>
      <label for="password">PW: </label>
      <input id="password" type="text" v-model="password">
    </div>
    <button type="submit">Login</button>
  </form>
  <ul>
    <li v-for="item in data" :key="item">{{ item.name }}</li>
  </ul>
</template>

<script>
import axios from 'axios';
import { ref } from 'vue';

export default {

  // composition API
  setup() {
    // data
    const userId = ref('');
    const password = ref('');
    const data = ref([]);

    // methods
    const submit = async function() {
      try {
        const res = await axios.get('https://jsonplaceholder.typicode.com/users/', {
          userId : userId.value,    //
          password: password.value  //
        });
        this.data = res.data;
      } catch (e) {
        console.log(e);
      }
    }

    return { userId, password, data, submit } // return 한 값들은 option에서 사용 가능
  },

  // 기존 option 설정
  // data() {
  //   return {
  //     userId: '',
  //     password: '',
  //     data: [],
  //   }
  // },
  // methods: {
  //   async submit() {
  //     try {
  //       const data = {
  //         userId : this.userId,
  //         password: this.password
  //       }
  //       const res = await axios.get('https://jsonplaceholder.typicode.com/users/', data);
  //       this.data = res.data;

  //     } catch (e) {
  //       console.log(e);
  //     }
  //   }
  // }
}
</script>

<style>
form { display: block; width: 15rem; }
form > div { display: flex; align-items: center; justify-content: space-between; }
form > div + div { margin-top: .4rem; }
form > div > label { flex: 0 0 3rem; }
form > div > input { flex: 1 1 auto; }
form > button { width: 100%; margin-top: 1rem; }
</style>
