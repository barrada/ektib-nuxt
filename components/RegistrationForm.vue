<template>
     <v-form id="signup-form" action="post" class=""> 
     
        <section v-if="step == 1"> 
            <!-- <h1 class="">Register</h1> -->
            <h5>step1</h5>
						<v-text-field v-model="name" placeholder="Name" solo> </v-text-field>
						<v-text-field v-model="emailorphone" placeholder="Email or Phone" solo> </v-text-field>
            <v-text-field
						solo
						 background-color="#343c4b"  
						type="text" @input="test" v-model="form.username" placeholder="username" class="form-control form-control-lg"> 
						</v-text-field>
            <button @click.prevent="next" class="btn" v-bind:class="{ disabled: !isActive,'btn-info':isActive }">next</button>
        </section>
         <section v-if="step == 2"> 
            <h5>step2</h5>
              <button @click.prevent="back" class="btn">back</button>
             <button @click.prevent="next" class="btn">next</button>
           
        </section>
         <section v-if="step == 3"> 
            <h5>step3</h5>
              <button @click.prevent="back" class="btn">back</button>
             <button @click.prevent="next" class="btn">next</button>
        </section>
         <section v-if="step == 4"> 
            <h5>step4</h5>
              <button @click.prevent="back" class="btn">back</button>
             <button @click.prevent="next" class="btn">next</button>
        </section>
         <section v-if="step == 5"> 
            <h5>step5</h5>
            <button @click.prevent="back" class="btn">back</button>
            <input type="submit" value="Sign Up" @click.prevent="signup" class="btn">
        </section>
        <section v-if="step == 6"> 
            <h5>step6</h5>
               {{ activate}}
        </section>
      
     
    </v-form>
</template>
<script>
export default {
    name:"RegistrationForm",
    data(){
    return{
        step:1,
        steps:6,       
        activate:null,
        isActive:false,
        form:{
            username:null
        }
    }
  },
  methods:{
    next:function(){
        if(this.step==1){
            if(!this.form.username){
                return false
            }
        }
        this.isActive=true
        this.step++
    },
    back:function(){
        this.step--
    },
    signup:function(){
    //   alert("dones")
     
      this.activate="please check your email and activate your account"
      this.step=6
      
    },
    test:function(){
       if(this.form.username){
           this.isActive=true
       }else{this.isActive=false}
    
 
    }    
  }
}
</script>
<style>
.disabled{
    /* color:red; */
    /* background-color:red */
}
</style>