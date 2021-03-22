<template>
<div id="left">
          <div id="signin">
            <div class="logo">
              <h2>Buscaminas</h2>
            </div>
            <b-form @submit="onSubmit" @reset="onReset" v-if="show">
              <b-form-group
                id="input-group-1"
                label-for="input-1"
                label="Email address:"
                description="We'll never share your email with anyone else."
              >
                <b-form-input
                  id="input-1"
                  v-model="form.email"
                  type="email"
                  placeholder="Enter email"
                  required
                  class="text-input"
                ></b-form-input>
                
              </b-form-group>
              <b-form-group
                id="input-group-1"
                label-for="input-2"
                label="Password:"
              >
                <b-form-input
                  id="input-2"
                  v-model="form.password"
                  type="password"
                  placeholder="Enter password"
                  required
                  class="text-input"
                ></b-form-input>
                
              </b-form-group>
              <button type="submit" class="primary-btn">Sign in</button>
            </b-form>
            <div class="links">
              <a href="#">Forgot Password?</a>
            </div>
            <hr class="bar" />
            <a href="#" class="secondary-btn">Create an account</a>
          </div>
          <footer id="main-footer">
            <p>Copyright &copy; 2020, Nestozo_Dev All Rights Reserved</p>
            <!-- <div>
              <a href="#">terms of use</a> | <a href="#">Privacy Policy</a>
            </div> -->
          </footer>
        </div>
  <!-- <b-container fluid>
    <b-row>
      <b-col align-self="center">
        <b-card
          title="Buscaminas"
          img-src="https://picsum.photos/600/300/?image=25"
          img-alt="Image"
          tag="article"
          
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
    </b-row>
    
  </b-container> -->
</template>
<script>
// import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'Login',
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

</style>