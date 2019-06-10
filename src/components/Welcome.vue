<template>
    
    <div class="container">

    <!-- Outer Row -->
    <div class="row justify-content-center">

      <div class="col-xl-10 col-lg-12 col-md-9">

        <div class="card o-hidden border-0 shadow-lg my-5">
          <div class="card-body p-0">
            <!-- Nested Row within Card Body -->
            <div class="row">
              <div class="col-lg-6 d-none d-lg-block bg-login-image"></div>
              <div class="col-lg-6">
                <div class="p-5">
                  <div class="text-center">
                    <h1 class="h4 text-gray-900 mb-4">Bienvenido!</h1>
                  </div>
                  <form class="user">
                    <div class="form-group">
                      <input type="email" v-model="email" class="form-control form-control-user" id="exampleInputEmail" aria-describedby="emailHelp" placeholder="Ingrese correo...">
                    </div>
                    <div class="form-group">
                      <input type="password" v-model="password" class="form-control form-control-user" id="exampleInputPassword" placeholder="Contraseña">
                    </div>
                    <a v-on:click="login" class="btn btn-primary btn-user btn-block" style="color:white">
                      Ingresar
                    </a>
                  </form>
                  <hr>
                  <div v-on:click="toReg" class="text-center">
                    <a class="btn-block" >Crear una cuenta</a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

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
    },
    toReg(){
      console.log('working')
      var comp = 'Join'
      this.$emit('swapcomp',comp);
      console.log(comp)
    }
  }
}
</script>