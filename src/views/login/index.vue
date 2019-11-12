<template>
  <div id="app">
    <div id="login-box">
      <el-form
        ref="LoginForm"
        :model="loginForm"
        :rules="loginformrules"
      >
        <el-form-item prop="mobile">
          <el-input placeholder="请输入手机号码" v-model="loginForm.mobile"></el-input>
        </el-form-item>
        <el-form-item prop="code">
          <el-input placeholder="请输入校验码" v-model="loginForm.code"></el-input>
        </el-form-item>
        <el-form-item>
          <el-checkbox v-model="loginForm.xieyi"></el-checkbox>
          <span>我同意当前协议</span>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" style="width:100%;">登录</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      LoginForm: {
        mobile: '',
        code: '',
        xieyi: false
      },
      loginformrules: {
        mobile: [
          { required: true, message: '请输入正确的手机号码', trigger: 'blur' }
        ],
        code: [
          { required: true, message: '请输入正确的验证码', trigger: 'blur' }
        ]
      }
    }
  }
}
</script>

<style lang="less" scoped>
#app {
  background-color: green;
  display: flex;
  justify-content: center;
  align-items: center;
  #login-box {
    width: 400px;
    height: 300px;
    background-color: #ccc;
    box-sizing: border-box;
    padding: 30px;
  }
}
</style>
