<template>
<div id="main">
  <div class="login-container" v-show="isLogin">
        <div class="d-flex align-items-center justify-content-center bg-br-primary ht-100v">
            <div class="login-wrapper wd-300 wd-xs-350 pd-25 pd-xs-40 bg-white rounded shadow-base">
                <div class="text-center"><img src="" width="50%" /></div>
                <div class="signin-logo tx-center tx-28 tx-bold tx-inverse mg-b-10"><span class="tx-normal">[</span> Stock Market <span class="tx-normal">]</span></div>

                <div id="alertWithIcon" style="display:none;">
                    <div class="alert alert-danger" role="alert">
                        <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                        </button>
                        <div class="d-flex align-items-center justify-content-start">
                            <span><strong id="msg"></strong></span>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <input type="text" class="form-control input-login" id="userName" v-model="userModel.userName" placeholder="Enter Username">
                    <!--<small v-show="isSubmitted && !userModel.userName" class="tx-danger">User Name is Required</small>-->
                </div><!-- form-group -->
                <div class="form-group">
                    <input type="password" class="form-control input-login" id="pin" v-model="userModel.password" placeholder="Enter Password" v-on:keyup.enter="login">
                    <!--<small v-show="isSubmitted && !userModel.password" class="tx-danger">User Name is Required</small>-->
                    
                </div><!-- form-group -->
                <button v-on:click="login" id="Login" type="submit" class="btn btn-primary active  btn-block mg-b-10">  Log me in</button>

            </div><!-- login-wrapper -->
        </div><!-- d-flex -->

    </div>
    <Layout v-show="isLayout"></Layout>


    <!-- Sign up  -->
    <div class="login-container" v-show="isSignup">
        <div class="d-flex align-items-center justify-content-center bg-br-primary ht-100v">
            <div class="login-wrapper wd-300 wd-xs-350 pd-25 pd-xs-40 bg-white rounded shadow-base">
                <div class="text-center"><img src="" width="50%" /></div>
                <div class="signin-logo tx-center tx-28 tx-bold tx-inverse mg-b-10"><span class="tx-normal">[</span> Auxxa - Suite 1.0 <span class="tx-normal">]</span></div>

                <div id="alertWithIcon" style="display:none;">
                    <div class="alert alert-danger" role="alert">
                        <button type="button" class="close" data-dismiss="alert" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                        </button>
                        <div class="d-flex align-items-center justify-content-start">
                            <span><strong id="msg"></strong></span>
                        </div>
                    </div>
                </div>

                <div class="form-group">
                    <input type="text" class="form-control input-login" v-model="userModel.userName" placeholder="Enter Username">
                    <!--<small v-show="isSubmitted && !userModel.userName" class="tx-danger">User Name is Required</small>-->
                </div><!-- form-group -->
                <div class="form-group">
                    <input type="password" class="form-control input-login" v-model="userModel.password" placeholder="Enter Password" v-on:keyup.enter="login">
                    <!--<small v-show="isSubmitted && !userModel.password" class="tx-danger">User Name is Required</small>-->
                    
                </div><!-- form-group -->
                <button v-on:click="login" type="submit" class="btn btn-primary active  btn-block mg-b-10">  Log me in</button>

            </div><!-- login-wrapper -->
        </div><!-- d-flex -->

    </div>


    <!-- End Sign up -->
  </div>
</template>

<script>
import Layout from "@/components/Layout";
import Login from "@/components/Login";

export default {
  name: "App",
  components: { Layout, Login },
  data() {
    return{
      isLogin: true,
      isSignup: false,
      isLayout: false,
    userModel: {
        userName: "",
        password: ""
      }
    }
    
  },
  methods: {
    login: function() {
      this.isLogin = false;
      this.isLayout = true;
      this.isSignup = false;
      
    },
    changecomponent: function() {}
  }
};
</script>


