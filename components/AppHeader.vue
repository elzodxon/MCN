<template>
  <div class="AppHeader" :class="{change_color: scrollPosition > 50}">
    <div class="container">
      <div class="rectangle" style="background: #02F093;
border-radius: 0px 0px 5px 5px;
 height: 4px; width: 100%">
      </div>
    </div>
    <div class="container pt-5">
      <div class="row align-items-center">
        <div class="col-2">
          <div class="wrapper">
            <nuxt-link to="/">
              <svg width="95" height="30" viewBox="0 0 95 30" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M30.0029 0.655737V29.3443H21.7829V15.3689L15.3713 26.1066H14.6315L8.21996 15.3689V29.3443H0V0.655737H8.21996L15.0014 12.3361L21.7829 0.655737H30.0029Z"
                  fill="#02F093"/>
                <path
                  d="M52.2852 30C47.9561 30 44.3667 28.5656 41.5171 25.6967C38.6675 22.8279 37.2427 19.2623 37.2427 15C37.2427 10.7377 38.6675 7.17213 41.5171 4.30328C44.3667 1.43443 47.9561 0 52.2852 0C54.943 0 57.3953 0.628415 59.6421 1.88525C61.8889 3.14208 63.6425 4.83607 64.9029 6.96721L57.7515 11.0656C57.2857 10.1366 56.5596 9.39891 55.5732 8.85246C54.5868 8.30601 53.4908 8.03279 52.2852 8.03279C50.2576 8.03279 48.6137 8.68852 47.3533 10C46.0929 11.3115 45.4627 12.9781 45.4627 15C45.4627 17.0219 46.0929 18.6885 47.3533 20C48.6137 21.3115 50.2576 21.9672 52.2852 21.9672C53.5182 21.9672 54.6142 21.694 55.5732 21.1475C56.5596 20.6011 57.2857 19.8497 57.7515 18.8934L64.9029 22.9918C63.6425 25.1503 61.8889 26.8579 59.6421 28.1148C57.3953 29.3716 54.943 30 52.2852 30Z"
                  fill="#02F093"/>
                <path
                  d="M86.78 0.655737H95V29.3443H88.424L79.3821 16.2295V29.3443H71.1621V0.655737H77.7381L86.78 13.7705V0.655737Z"
                  fill="#02F093"/>
              </svg>
            </nuxt-link>
          </div>
        </div>
        <div class="col-5">
          <ul class="nav-list">
            <li class="nav-list-item">
              <nuxt-link to="/projects">Наши проекты</nuxt-link>
            </li>
            <li class="nav-list-item">
              <nuxt-link to="/portfolio/instagram">Портфолио</nuxt-link>
            </li>
            <li class="nav-list-item">
              <nuxt-link to="/contact">Контакты</nuxt-link>
            </li>
          </ul>
        </div>
        <div class="offset-1 col-4">
          <div class="col-wrapper d-flex align-items-center justify-content-between">
            <div>
              <b-form-select class="lang-select" v-model="selected" :options="options"></b-form-select>
            </div>
            <div class="mybtn">
              <div>
                <b-button id="show-btn" @click="$emit('modalOpen')">Оставить заявку</b-button>
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


  name: 'AppHeader',

  data() {
    return {
      selected: null,
      options: [
        {value: null, text: 'Русский'},
        {value: 'a', text: 'Uzbek'},
        {value: 'b', text: 'English'},
      ],
      scrollPosition: null

    }
  },
  methods: {
    handleScroll: (event, el) => {
      if (window.scrollY >= 300) {
        el.classList.add('fixed');
      } else {
        el.classList.remove('fixed');
      }
    },
    updateScroll() {
      this.scrollPosition = window.scrollY
    }
  },
  mounted() {
    window.addEventListener('scroll', this.updateScroll);
  },
}
</script>

<style lang="scss">
.AppHeader {
  transition: all 0.5s;
  padding-bottom: 40px;
}
.mybtn  a {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 10px;
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: 25px;
  letter-spacing: 0em;
  color: #262626;
  background: #02F093;
  height: 57px;
  width: 214px;
  text-align: center;
  border: none;

  &:hover {
    text-decoration: none;
  }
}


.change_color {
  background-color: #151515;
  z-index: 111;
}

ul {
  margin: 0;
}

/* Nav list */
.nav-list-item a {
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: center;
  color: #F6F6F6;

}

.nav-list-item a:hover {
  text-decoration: none;
}

/* Lang Select */
.lang-select {

}


/* myBTN */
div.mybtn .btn {
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: 25px;
  letter-spacing: 0em;
  color: #262626;
  background: #02F093;
  height: 57px;
  width: 214px;
  text-align: center;
  border: none;
}

option {
  background: black;
}

.custom-select {
  border: none;
  background: none;
  color: #F6F6F6;
  font-size: 16px;
  font-style: normal;
  font-weight: 600;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: center;
  outline: none;
}

.custom-select:focus {
  outline: none;
  border: none;
}

.AppHeader {
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 150;
}

.nav-list {
  display: flex;
  align-items: center;
  justify-content: space-between;
  list-style: none;
}

/* Modal */
.modal-md {
  max-width: 100%;
  margin: 0;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  height: 100vh;
  display: flex;
  position: fixed;
  z-index: 100000;
  width: 100%;
  padding: 0;
}

.modal-header{
  border: none;
}
</style>
