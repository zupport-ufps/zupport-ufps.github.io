<template>
  <component v-on:login="login" v-bind:is="currentcomp"></component>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Welcome from './components/Welcome.vue'
import Platform from './components/Platform.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    Welcome,
    Platform
  },
  data(){
    return{
      currentcomp:'Welcome'
    }
  },
  methods:{
    swapcomp: function(comp){
      this.currentcomp=comp
    },
    login: function(email,password){
      var self = this
      localStorage.clear()
      console.log('working');
      axios.post('https://zupport.herokuapp.com/login/',{
        email: email,
        password: password
      }).then(function(response){

        localStorage.setItem('id',response.data.id)
        localStorage.setItem('permisos',response.data.permisos)
        localStorage.setItem('token',response.data.token)
        console.log(localStorage);
        self.currentcomp='Platform';
      });

    }

  }
}
</script>