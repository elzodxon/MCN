<template>
  <div>
    <div class="projects-page">
      <PortfolioMain :instagram="instagram1"/>
    </div>
    <PortfolioItems :profiles="profiles" />
  </div>
</template>

<script>
import PortfolioMain from '@/components/PortfolioMain'
import PortfolioItems from '@/components/PortfolioItems'

export default {
  data() {
    return {
      instagram1: {
        text1: 'Сотрудничество с Instagram инфлюенсерами',
        text2: 'Мы тесно сотрудничаем и с наиболее популярными узбекистанскими Instagram инфлюенсерами. Также предоставляя им различные услуги и оказывая помощь в их продвижении.',
        img: '/img/help.png'
      },
      profiles:[
        {
          nick: 'leo_17s',
          name: 'Shakhzoda Salimjanova',
          followers: '1 млн.',
          img: "/img/leo.png"
        },
        {
          nick: 'diiray',
          name: 'Diana R.',
          followers: '298 тыс.',
          img: '/img/diana.png'
        },
        {
          nick: 'selivanna_muse',
          name: 'Selivanna Sin',
          followers: '19,6 тыс.',
          img: '/img/selivanna.png'
        },
        {
          nick: 'ofamur',
          name: 'Ofeliya Muradova',
          followers: '243 тыс.',
          img: '/img/ofamur.png'
        },
        {
          nick: 'familytravel.uz',
          name: 'Familiy Travel',
          followers: '93,3 тыс.',
          img: '/img/familiytravel.png'
        },
        {
          nick: 'rebekkochka',
          name: 'Rebekka',
          followers: '190 тыс.',
          img: '/img/rebekka.png'
        },
        {
          nick: 'shadisha_',
          name: 'Shadisha',
          followers: '37,3 тыс.',
          img: '/img/shabisha.png'
        },
        {
          nick: 'durdona_kurbonova',
          name: 'Durdona Qurbonova',
          followers: '2.6 млн.',
          img: '/img/durdona.png'
        },
      ]
    }
  },
  components: {
    PortfolioMain,
    PortfolioItems
  }
}
</script>
<style>
.projects-page {
  background-image: url("/img/back-instagram.png");
  background-repeat: no-repeat;
  background-size: cover;
  height: 100vh;
  background-position: center;
  padding: 210px 0 0 0;
}
</style>
