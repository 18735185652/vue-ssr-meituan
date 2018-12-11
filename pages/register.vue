<template>
  <div class="page-register">
    <article class="header">
      <header>
        <a
          href="/"
          class="site-logo"/>
        <span class="login">
          <em class="bold">已有美团账号?</em>
          <a href="/login">
            <el-button
              type="primary"
              size="small">登录</el-button>
          </a>
        </span>
      </header>
    </article>
    <section>
      <el-form
        ref="ruleForm"
        :rules="rules"
        :model="ruleForm"
        label-width="100px"
        class="demo-ruleForm"
      >
        <el-form-item
          label="昵称"
          prop="name">
          <el-input v-model="ruleForm.name"/>
        </el-form-item>

        <el-form-item
          label="邮箱"
          prop="email">
          <el-input v-model="ruleForm.email "/>
          <el-button
            size="mini"
            round
            @click="sendMsg">发送验证码</el-button>
          <span class="status">{{ statuMsg }}</span>
        </el-form-item>
        <el-form-item
          label="验证码"
          prop="code">
          <el-input
            v-model="ruleForm.code"
            maxlength="4"
          />
        </el-form-item>
        <el-form-item
          label="密码"
          prop="pwd">
          <el-input
            v-model="ruleForm.pwd"
            type="password"
          />
        </el-form-item>
        <el-form-item
          label="确认密码"
          prop="cpwd">
          <el-input
            v-model="ruleForm.cpwd"
            type="password"/>
        </el-form-item>
        <el-form-item>
          <el-button
            type="primary"
            @click="register"
          >同意以下协议并注册</el-button>
          <div class="error">{{ error }}</div>
        </el-form-item>
        <el-form-item>
          <a
            href="http://www.meituan.com/about/terms"
            target="_blank">《美团用户协议》</a>
        </el-form-item>
        
      </el-form>
    </section>
  </div>
</template>
<script>
  export default {
    data(){
      return {
        statuMsg:'',
        error:'',
        ruleForm:{
          name:'',
          code:'',
          email:'',
          pwd:'',
          cpwd:''
        },
        rules:{
          name:[{
            required:true,
            type:"string",
            message:'请输入昵称',
            trigger:'blur'
          }],
          email:[
            {
              validator:(rule,value,callback)=>{
                if(value===''){
                  callback(new Error('请输入内容'))
                }else{
                  callback();
                }
              },
              trigger:'blur'
            },{
            required:true,
            type:'email',
            message:'请输入正确的邮箱',
            trigger:'blur'
          }],
          pwd:[{
            required:true,
            message:'创建密码',
            trigger:'blur'
          }],
          cpwd:[{
            required:true,
            message:'确认密码',
            trigger:'blur'
          },{
              validator:(rule,value,callback)=>{
                if(value===''){
                  callback(new Error('请再次输入密码'))
                }else if(value!==this.ruleForm.pwd){
                  callback(new Error('两次输入密码不一致'))
                }else{
                  callback();
                }
              },
              trigger:'blur'
          }],
        }
      }
    },
    layout: 'blank',

    methods:{
      sendMsg(){
        alert(1);
      },
      register(){
        alert("register");
      }
    }
  }
</script>
<style lang="scss">
  @import "@/assets/css/register/index.scss";
</style>
