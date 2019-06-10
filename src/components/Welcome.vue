<template>
    
    <div class="container-fluid fullH">

      <div class="row">
        <div class="col-lg-6 offset-lg-3">
          <div class="card vmiddle">
          <article class="card-body">
          <a href="" class="float-right btn btn-outline-primary">Ya tienes cuenta?</a>
          <h4 class="card-title mb-4 mt-1">Bienvenido a Zupport</h4>
            <form>
              <div class="form-group">
                <label>Correo</label>
                  <input name="" class="form-control" v-model="email" placeholder="Correo electronico registrado" type="email">
              </div> <!-- form-group// -->
              <div class="form-group">
                <a class="float-right" href="#">Lo olvidaste?</a>
                <label>Contraseña</label>
                  <input class="form-control" v-model="password" placeholder="******" type="password">
              </div> <!-- form-group// --> 
              <div class="form-group"> 
              <div class="checkbox">
                <label> <input type="checkbox"> Recordar contraseña </label>
              </div> <!-- checkbox .// -->
              </div> <!-- form-group// -->  
                                                                      
          </form>
            <div class="form-group">
                  <button v-on:click="login" class="btn btn-primary btn-block"> Entrar  </button>
              </div> <!-- form-group// -->   
          </article>
        </div> <!-- card.// -->
        </div>
      </div>
      
    </div>
    
</template>

<script>
export default {
  name: 'Welcome',
  data: function(){
    return{
      email:'',
      password:''
    }
  },
  methods:{
    login(){
      this.$emit('login',this.email,this.password)
    }
  }
}
</script>