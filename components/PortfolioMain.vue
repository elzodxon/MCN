<template>
  <div class="container" >
    <div class="row ">
      <div class="col-8">
        <div>
          <h1>{{ instagram.text1 }}</h1>
          <p>{{ instagram.text2 }}</p>
          <p>{{instagram.text3}}</p>
        </div>
      </div>
      <div class="col-4">
        <div class="wrapper">
          <div class="rectangle">
          </div>
          <div class="img-wrapper">
            <img :src="instagram.img" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: 'PortfolioMain',
  props: {
    instagram: {
      type: Object,
      default: {},
    },
  },

}
</script>


<style scoped>
h1 {
  color: white;
  font-size: 58px;
  font-style: normal;
  font-weight: 700;
  line-height: 75px;
  letter-spacing: 0em;
  text-align: left;
  padding-bottom: 32px;
}

p {
  font-size: 20px;
  font-style: normal;
  font-weight: 400;
  line-height: 32px;
  letter-spacing: 0em;
  text-align: justify;
  color: white;

}

.rectangle {
  border: 1px solid #02F093;
  height: 300px;
  width: 373px;
  position: relative;
}

.img-wrapper {
  position: absolute;
  top: 8%;
}
</style>
