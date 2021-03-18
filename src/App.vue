<template>
  <b-container fluid id="app">
    <b-row style="padding-top:60px;">
      <b-col></b-col>
      <b-col align-self="center">
        <b-card
          title="Buscaminas"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          tag="article"
          
          class="mb-5"
        >
          <b-card-text>
            <b-form @submit="onSubmit" @reset="onReset" v-if="show">
              <b-form-group
                id="input-group-1"
                label-for="input-1"
                description="We'll never share your email with anyone else."
              >
                <b-form-input
                  id="input-1"
                  v-model="form.email"
                  type="email"
                  placeholder="Enter email"
                  required
                ></b-form-input>
                
              </b-form-group>
              <b-form-group
                id="input-group-1"
                label-for="input-2"
              >
                <b-form-input
                  id="input-2"
                  v-model="form.password"
                  type="password"
                  placeholder="Enter password"
                  required
                ></b-form-input>
                
              </b-form-group>
                
            </b-form>
          </b-card-text>
          <b-container class="bv-example-row" >
            <b-row>
              <b-col cols="6">
                <b-button href="#" variant="outline-dark">Play as invited</b-button>
              </b-col>
              <b-col cols="2"></b-col>
              <b-col cols="4">
                <b-button href="#" variant="primary">Sign In</b-button>
              </b-col>
            </b-row>
          </b-container>
          <br>
          <br>
          <b-button variant="link">Sign Up</b-button>
        </b-card>
      </b-col>
      <b-col></b-col>
    </b-row>
    
  </b-container>
</template>
<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'App',
  // components: {
  //   HelloWorld
  // }
  data() {
      return {
        form: {
          email: '',
          password: '',
          name: '',
          food: null,
          checked: []
        },
        foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
        show: true
      }
    },
  methods: {
      onSubmit(event) {
        event.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(event) {
        event.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
  background-image: url('./assets/background_explosion.jpg');
  background-repeat: no-repeat;
  background-size: cover;
  
}
</style>
