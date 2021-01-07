<template>
  <div>
    <div class="projects-page">
      <PortfolioMain :instagram="instagram1"/>

    </div>

  </div>
</template>

<script>
import PortfolioMain from '@/components/PortfolioMain'
export default {
  data(){
    return{
      instagram1: {
        text1: 'Сотрудничество с Instagram инфлюенсерами',
        text2: 'Мы тесно сотрудничаем и с наиболее популярными узбекистанскими Instagram инфлюенсерами. Также предоставляя им различные услуги и оказывая помощь в их продвижении.',
        img: '/img/instagram.png'
      }
    }
  },
  components: {
    PortfolioMain
  }
}
</script>
<style>
.projects-page{
  background-image: url("/img/back-instagram.png");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  background-position: center;
  padding: 210px 0 0 0;
}
</style>
