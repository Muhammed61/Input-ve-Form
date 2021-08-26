<template>
  <div class="container">
    <form v-if="!isSubmitted">
      <div class="row" >
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
         
          <app-fullname v-model="fullname"></app-fullname>

          <div class="form-group">
            <label>E-mail bilgisi</label>
            <input type="text" class="form-control" v-model="email">
          </div>
          <div class="form-group">
            <label>Şifre bilgisi</label>
            <input type="password" class="form-control" v-model="password">
          </div>
          <div class="form-group">
            <label>
              <input type="radio" v-model="gender" value="kadin"> Kadın
            </label>
            <label>
              <input type="radio" v-model="gender" value="erkek"> Erkek
            </label>
          </div>
          <button @click.prevent="submit" class="btn btn-primary">Kayıt Ol</button>
          
        </div>
      </div>
    </form>
    <div v-else class="row">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-info">
          <div class="panel-heading">
            <h4>Girdiğiniz Bilgier</h4>
          </div>
          <div class="panel-body">
            <p>Tam Ad {{ fullname }}</p>
            <p>E-mail {{ email }}</p>
            <p>Şifre {{ password}}</p>
            <p>Cinsiyet {{ gender }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import Fullname from "./Fullname";

  export default {
    components : {
      appFullname : Fullname
    },
    data(){
      return {
        // firstName : '',
        // lastName : '',
        fullname : 'Muhammed Günaydın',
        email : '',
        password : '',
        gender : '',
        isSubmitted : false
      }
    },
    methods : {
      submit(){
        this.isSubmitted = true;
      }
    }
  }
</script>

<style>
</style>
