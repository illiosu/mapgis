<template>
  <div class="login">
    <section class="form_container">
      <div class="manage_tip">
<<<<<<< HEAD
        <span class="title">WebGIS DEMO展示系统</span>
=======
        <span class="title"> 水污染监测系统</span>
>>>>>>> bb3d1b7 (增加了大屏)
      </div>
      <el-form :model="loginUser" :rules="rules" ref="loginForm" class="loginForm" label-width="60px">
        <el-form-item label="邮箱" prop="email">
          <el-input v-model="loginUser.email" placeholder="请输入邮箱"></el-input>
        </el-form-item>
        <el-form-item label="密码" prop="password">
          <el-input v-model="loginUser.password" placeholder="请输入密码" type="password"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="submitForm('loginForm')" class="submit_btn">登 录</el-button>
        </el-form-item>
        <div class="tiparea">
          <p>
            还没有账号？现在
            <router-link to="/register">注册</router-link>
          </p>
        </div>
      </el-form>
    </section>
  </div>
</template>

<script>
import jwt_decode from 'jwt-decode' //解析token的模块

export default {
  name: "login",
  data() {
    return {
      loginUser: {
        email: "2500509095@qq.com",
        password: "123456"
      },
      rules: {
        email: [
          {
            type: "email",
            required: true,
            message: "邮箱格式不正确",
            trigger: "change"
          }
        ],
        password: [
          { required: true, message: "密码不能为空", trigger: "blur" },
          { min: 6, max: 30, message: "长度在 6 到 30 个字符", trigger: "blur" }
        ]
      }
    }
  },
  methods: {
     submitForm(formName) {
      this.$refs[formName].validate(valid => {
      
        if (valid) {
          this.$router.push("/index")
          this.$axios
            .post("/api/users/login", this.loginUser)
            .then(res => {
              // console.log(res)
              //token处理
              const { token } = res.data
              //存储到localstorage里
              localStorage.setItem("eletoken", token)
              //解析token
              const decode = jwt_decode(token)
              console.log(decode)
               // 存储数据到VUEX中 
              this.$store.dispatch("setIsAutnenticated", !this.isEmpty(decode))
              this.$store.dispatch("setUser", decode)

              this.$router.push("/index")
            })
        } else {
          console.log("error submit!!")
          return false;
        }
      });
    },
    isEmpty(value) {
      return (
        value === undefined ||
        value === null ||
        (typeof value === "object" && Object.keys(value).length === 0) ||
        (typeof value === "string" && value.trim().length === 0)
      )
    }
  },
}
</script>


<style scoped>
.login {
  position: relative;
  width: 100%;
  height: 100%;
<<<<<<< HEAD
  background: url(../assets/bg.jpg) no-repeat center center;
=======
  background: url(../assets/bing.jpg) no-repeat center center;
>>>>>>> bb3d1b7 (增加了大屏)
  background-size: 100% 100%;
}
.form_container {
  width: 370px;
  height: 210px;
  position: absolute;
  top: 20%;
  left: 60%;
  padding: 25px;
  border-radius: 5px;
  text-align: center;
}
.form_container .manage_tip .title {
  font-family: "Microsoft YaHei";
  font-weight: bold;
  font-size: 28px;
  color: #fff;
}
.loginForm {
  margin-top: 20px;
  background-color: #fff;
  padding: 20px 40px 20px 20px;
  border-radius: 5px;
  box-shadow: 0px 5px 10px #cccc;
}

.submit_btn {
  width: 100%;
}
.tiparea {
  text-align: right;
  font-size: 12px;
  color: #333;
}
.tiparea p a {
  color: #409eff;
}
</style>