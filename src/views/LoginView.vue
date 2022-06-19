<template>
    <div class="login-icon">
      <img src="#" alt="">
    </div>
    <div class="login-container">
      <div class="login-box">
        <!-- 標題 -->
        <h1>雲端數據流量系統<br>登入</h1>
          <!-- 表單 -->
        <!-- 登入帳號 -->
        <div class="form-group form-inline">
          <label for="username" class="form-label">帳號</label>
          <input type="text" class="form-control" id="username" placeholder="請輸入您的帳號" v-model="username">
        </div>
        <!-- 登入密碼 -->
        <div class="form-group form-inline">
          <label for="password">密碼</label>
          <input
            type="password"
            class="form-control ml-2"
            id="password"
            placeholder="請輸入登入密碼"
            v-model="password"
          />
        </div>
        <!-- 登入按鈕 -->
        <div class="form-group form-inline">
         <button type="button" class="btn btn-primary" @click="onLoginClick">登入</button>
        </div>
      </div>
       <footer class="footer">
      <div class="copyright">
        <p>Copyright © 2022 宏碁智雲資訊股份有限公司 Acer AI Cloud Inc. All Rights Reserved.</p>
      </div>
    </footer>
      </div>

</template>

<script>
export default {
  name: 'MyLogin',
  data () {
    return {
      username: '',
      password: ''
    }
  },
  methods: {
    onLoginClick () {
      if (this.username === 'admin' && this.password === '123456') {
        // 登入成功跳轉到home頁面
        this.$router.push('/home')
        localStorage.setItem('token', 'Bearer xxx')
      } else {
        localStorage.removeItem('token')
      }
    }
  }
}
</script>

<style scoped>
/* .login-icon{
  height: 50vh;
} */
/* *{
  box-sizing: border-box;
} */

.login-container{
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: white;
  height: 100vh;
  position: relative;
}

.login-container::before{
  content: '';
  position: absolute;
  width: 100%;
  background-color: #1C3A5E;
  height: 50%;
  bottom:0;
}

.login-box{
  position: absolute;
  padding: 50px;
  width: 780px;
  background-color: #EEEEEE;
  border-radius: 10px;
  z-index: 999;
}

.footer{
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}

.copyright {
  color: white;

}
</style>
