<template>
  <div class="login-wrap">
    <div class="ms-title">联想法内隐意识分析软件</div>
    <div class="ms-login">
      <el-form :model="param" :rules="rules" ref="login" label-width="0px" class="ms-content">
        <el-form-item prop="username">
          <el-input v-model="param.username" placeholder="username">
            <el-button slot="prepend" icon="el-icon-lx-people"></el-button>
          </el-input>
        </el-form-item>
        <el-form-item prop="password">
          <el-input
            type="password"
            placeholder="password"
            v-model="param.password"
            @keyup.enter.native="submitForm()"
          >
            <el-button slot="prepend" icon="el-icon-lx-lock"></el-button>
          </el-input>
        </el-form-item>
        <div class="login-btn">
          <el-button class="login" @click="submitForm()">登 录</el-button>
        </div>
        <p class="login-tips">Tips : 用户名和密码随便填。</p>
      </el-form>
    </div>
    <div class="footer">

    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      param: {
        username: "admin",
        password: "123123"
      },
      rules: {
        username: [
          { required: true, message: "请输入用户名", trigger: "blur" }
        ],
        password: [{ required: true, message: "请输入密码", trigger: "blur" }]
      }
    };
  },
  methods: {
    submitForm() {
      this.$refs.login.validate(valid => {
        if (valid) {
          this.$message.success("登录成功");
          localStorage.setItem("ms_username", this.param.username);
          this.$router.push("/");
        } else {
          this.$message.error("请输入账号和密码");
          console.log("error submit!!");
          return false;
        }
      });
    }
  }
};
</script>

<style scoped>
.login-wrap {
  position: relative;
  width: 100%;
  height: 100%;
  background: url(../../assets/img/bg1.png) no-repeat;
  background-size: contain;
}
.ms-title {
  width: 100%;
  line-height: 50px;
  padding-top: 5%;
  text-align: center;
  font-size: 38px;
  color: #fff;
  font-weight: bolder
}
.ms-login {
  position: absolute;
  left: 50%;
  top: 50%;
  width: 350px;
  margin: -190px 0 0 -175px;
  border-radius: 20px;
  background: #fff;
  overflow: hidden;
  border: 15px solid rgb(174, 212, 174);
}
.ms-content {
  padding: 30px 30px;
}
.login-btn {
  text-align: center;
}
.login-btn button {
  width: 100%;
  height: 42px;
  margin-bottom: 10px;
  background: rgb(24, 219, 122);
  color: #fff;
  font-size: 18px;
}
.login-tips {
  font-size: 12px;
  line-height: 30px;
  color: #24b92c;
}
</style>