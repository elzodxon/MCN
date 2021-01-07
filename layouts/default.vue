<template>
  <div>
    <AppHeader @modalOpen="$bvModal.show('bv-modal-example')" />
    <b-modal id="bv-modal-example" hide-footer hide-header>
      <div class="container modal-container">
        <div class="row">
          <div class="col-1 offset-11">
            <svg  width="29" height="29" viewBox="0 0 29 29" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect x="0.284302" y="0.707031" width="1" height="39" transform="rotate(-45 0.284302 0.707031)" fill="white"/>
              <rect width="1" height="39" transform="matrix(-0.707107 -0.707107 -0.707107 0.707107 28.2843 0.707031)" fill="white"/>
            </svg>
          </div>
        </div>

        <div class="row">
            <div class="col-6 offset-3">
              <b-form @submit="onSubmit" v-if="show">

                <b-form-group id="input-group-2" label="ФИО" label-for="input-2">
                  <b-form-input
                    id="input-2"
                    v-model="form.name"
                    placeholder="Талипова Зилола"
                    required
                  ></b-form-input>
                </b-form-group>

                <b-form-group id="input-group-2" label="Контактный телефон" label-for="input-2">
                  <b-form-input
                    id="input-2"
                    v-model="form.number"
                    placeholder="+998 91 999 99 99"
                    v-mask="'+### ## ### ## ##'"
                    required
                  ></b-form-input>
                </b-form-group>


                <b-form-group id="input-group-3" label="Food:" label-for="input-3">
                  <b-form-select
                    id="input-3"
                    v-model="form.food"
                    :options="foods"
                    required
                  ></b-form-select>
                </b-form-group>


                <b-button type="submit" variant="primary">Submit</b-button>
              </b-form>

            </div>

        </div>
      </div>
    </b-modal>
    <Nuxt/>
    <AppFooter/>
  </div>
</template>


<script>
import Vue from 'vue'
import AppHeader from "../components/AppHeader";
import AppFooter from "../components/AppFooter";
Vue.use(VueMask)

import VueMask from 'v-mask'
// Vue.use(VueMask);
//
// // Or as a directive
// import { VueMaskDirective } from 'v-mask'
// Vue.directive('mask', VueMaskDirective);
//
// // Or only as a filter
// import { VueMaskFilter } from 'v-mask'
// Vue.filter('VMask', VueMaskFilter)

export default {
  components: {
    AppFooter,
    AppHeader
  },
  data(){
    return{
    form: {
      number: null,
      name: '',
      food: null,
      checked: []
    },
    foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
    show: true
  }},

  methods: {
    onSubmit(event) {
      event.preventDefault()
      alert(JSON.stringify(this.form))
    },
  }
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:ital,wght@0,200;0,300;0,400;0,600;0,700;0,900;1,200;1,300;1,400;1,600;1,700;1,900&display=swap');

*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
  font-family: 'Source Sans Pro', sans-serif;
}

ul li{
  list-style: none !important;
}


.modal-body{
  background-image: url("/img/backgroundform.png");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  background-position: center;
  padding: 210px 0 0 0;
}

.modal-container{
  margin-top: -100px;
}
</style>
