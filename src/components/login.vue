<template>
  <div class="login">
    <mu-container class="loginForm" @keyup.enter="login">
      <span v-if="error" style="color: red">用户名或者密码不能为空!</span>
      <span v-if="error1" style="color: red">用户名或者密码错误!</span>
      <mu-text-field v-model="value1" label="UserName" label-float help-text="用户名为6-12长度的字符"
                     icon="account_circle"></mu-text-field>
      <br/>
      <mu-text-field v-model="value2" label="Password" label-float icon="locked"></mu-text-field>
      <br/>
    </mu-container>
    <mu-button round class="btn" color="success" @click="login"> 点我登录</mu-button>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        msg: 'Welcome to Your Vue.js App',
        error: false,
        error1: false,
        value1: '',
        value2: ''
      }
    },
    methods: {
      login() {
        if (!this.value1 || !this.value2) {
          this.error1 = false;
          this.error = true;
          return;
        }
        if (this.value1 === 'huyuan' && this.value2 === '970618') {
          localStorage.setItem('user', 'huyuan');
          this.$router.push({
            name: 'home'
          })
        }else {
          this.error = false;
          this.error1 = true;
        }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="stylus">
  .login
    width 100vw
    height 100vh
    text-align center
    padding-top 40%
    background-color rgb(250, 250, 250)
    background-image url("./../assets/love/23.jpg")
    background-size 375px 100%
    background-repeat no-repeat
    .loginForm
      margin 0 auto
      font-size 16px
      .btn
        width 100px
</style>
