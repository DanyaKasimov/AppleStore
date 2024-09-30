<template>
  <div class="container">
    <h1 class="container_header">Support</h1>
    <div class="container_form">
      <form action="">
        <input class="title" type="text" placeholder="Title" v-model="formInfo.title" />
        <input class="title" type="email" placeholder="Email" v-model="formInfo.email" />
        <textarea class="message" placeholder="Message" v-model="formInfo.message" />
        <button class="button" @click="submit()">Отправить</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  name: "SupportPage",
  data(){
    return {
      formInfo: {
        title: '',
        message: '',
        email: '',
      }
    }
  },
  methods: {
    submit(){
      fetch("http://localhost:8090/auth/signup", {
        method: "POST",
        body: JSON.stringify({
          username: "Daneeilew123",
          email: "wwae@adaw",
          password:"2344"
        }),
        headers: {
          'Content-type': 'application/json; charset=UTF-8',
        },
      })
          .then((data) => console.log(data))
          .catch((err) => console.log(err))
    }
  }
};
</script>

<style scoped lang="scss" src="/src/assets/styles/lyaout/support.scss"></style>