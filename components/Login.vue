<template>
  <div id="wrapper">
    <v-row>
      <v-col cols="12" class="text-center">
        <img src="/logo.png" alt="" width="150px">
        <h1>Login</h1>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="11" lg="3" xl="3" md="3" class="mx-auto">
        <v-form ref="form" v-model="valid" lazy-validation>
          <v-text-field       
            v-model="username"
            solo
            hide-details="auto"
            :rules="nameRules"
            label="Email, Phone, or Username"
            required
            class="mb-3"
            background-color="#343c4b"
          ></v-text-field>
          <v-text-field
            v-model="password"
            :rules="[rules.required, rules.min]"
            solo

          
            :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'"
            :type="show1 ? 'text' : 'password'"
            name="input-10-1"
            label="Password"
            hint="At least 8 characters"
               background-color="#343c4b"
            @click:append="show1 = !show1"
            
          ></v-text-field>
          <v-btn
            :disabled="!valid"
            color="green"
            class="mr-4"
            @click="validate"
            width="100%"
          >
            Log in
          </v-btn>
        </v-form>
          <v-row class="mt-2 right pr-4 pl-4" style="font-size:13px;"><a href="/signup">Sign up</a> <v-spacer></v-spacer> <a href="/forgot"> Forgot password?</a> </v-row>
          <hr style="background-color:#343C4B;color:#343C4B;border:none;height:5px">
        <v-row class="px-4 ">   
           
              <span></span> <v-spacer></v-spacer><span>OR</span> <v-spacer></v-spacer> <br>
            
        </v-row>
     
         <v-btn color="white" justify="left" width="100%" class="mb-3">
             <!-- <v-icon left color="red">mdi-cloud-upload</v-icon> -->
             <img  src="/google-icon.svg"  alt="" width="22px" class="ml-n1"> 
                     <v-spacer></v-spacer>

             <span style="color:black">Log in with Google</span> 
              <v-spacer></v-spacer>
        </v-btn> 
         <v-btn color="#3B5998" width="100%"  class="">
             <!-- <v-icon left dark>mdi-cloud-upload</v-icon>
              -->
            <img src="/facebook-icon.svg" alt="" width="36px" class="ml-n3">
             <v-spacer></v-spacer>
             <span >Log in with Facebook </span>
              <v-spacer></v-spacer>
         </v-btn>
      </v-col>
    </v-row>
  </div>
</template>
<script>
export default {
	name:"Login",
    data () {
      return {
        show1: false,
        show2: true,
        show3: false,
        show4: false,
        password: 'Password',
        rules: {
          required: value => !!value || 'Required.',
          min: v => v.length >= 8 || 'Min 8 characters',
          emailMatch: () => ('The email and password you entered don\'t match'),
        },
      }
    },
}
</script>
<style scoped>
a{
  color:rgb(55, 172, 226);
  text-decoration:none;
  font-size:14px;
}
input {
}
</style>
