<template>
  <NavBar />
  <NavBarMobile />
  <MainWrapper @showDialog="showDialog" />
  <MyModal @hideDialog="hideDialog">
    <ContactSet />
  </MyModal>
</template>

<script>
import NavBar from '@/components/NavBar';
import NavBarMobile from '@/components/NavBarMobile';
import MainWrapper from '@/components/MainWrapper';
import MyModal from '@/components/UI/MyModal';
import ContactSet from '@/components/ContactSet';

export default {
  components: {
    NavBar,
    NavBarMobile,
    MainWrapper,
    MyModal,
    ContactSet
  },
  data() {
    return {
      
    }
  },
  mounted() {
    document.documentElement.classList.add('dark');
  },
  methods: {
    showDialog() {
        document.querySelector('.my-modal').classList.add('active');
    },
    hideDialog() {
      document.querySelector('.my-modal').classList.remove('active');
    }
  }
}
</script>


<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;800&display=swap');
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
/*==== VARIABLES ===================*/
:root {
  --navbar-width: 19%;
  --box-border-radius: 10px;
  --home-color: #9ad487;
  --about-color: #b09af8;
  --projects-color: #f8778a;
  --contact-color: #f1fc8b; 
  --primary-btn-color: #82DD85;
  --layout-color: #ee7d5b;
  --js-color: #e6d14c;
  --vue-color: #8cd6b5;
  --react-color: #7dc6d6;
  --blue: #007ACC;
}
html.dark {
  --main-bg-color: #0C0C0C;
  --main-bg-color-2: #565656;
  --default-text-color: #FFF;
  --navbar-bg-color: #212121;
  --navbar-mobile-bg-color: rgba(0,0,0,.8);
  --nav-item-bg:#2F2F2F;
  --nav-item-hover-bg: #403f3f;
  --regular-text-color: #AAAAAA;
  --regular-text-shadow: 0 0 3px #333;
  --section-heading-bg: #0C0C0C99;
  --section-heading-shadow: 2px 2px 4px rgb(0 0 0 / 50%);
  --section-text-bg: rgba(47, 47, 47, 0.9);
  --box-shadow: 0 0 32px 0 rgb(0 0 0 / 40%);
  --contact-item-hover-bg: #1a1a1a99;
  --box-border: none;
}
html.light {
  --main-bg-color: #FFF;
  --main-bg-color-2: #FFF;
  --default-text-color: #1C1C1E;
  --navbar-bg-color: #F2F2F2;
  --navbar-mobile-bg-color: rgba(200,200,200,.8);
  --nav-item-bg: #dbdbdb;
  --nav-item-hover-bg: #dcdce1;
  --regular-text-color: #5C5C5D;
  --regular-text-shadow: 1px 1.5px 0 #000;
  --section-heading-bg: transparent;
  --section-heading-shadow: 2px 2px 4px rgb(0,0,0);
  --section-text-bg: #FDFDFD;
  --box-shadow: none;
  --contact-item-hover-bg: #e7e4e499;
  --box-border: 1px solid #555;
}
/*====COMMON=================*/
html, body {
  background-color: var(--main-bg-color);
  transition: opacity .2s ease;
}
#app {
  min-height: 100vh;
  width: 100%;
  overflow-x: hidden;
  background-color: var(--main-bg-color);
  background: radial-gradient(50% 50% at top center,var(--main-bg-color-2),var(--main-bg-color));
  background-attachment: fixed;
  color: var(--default-text-color);
  font-family: 'Poppins', sans-serif;
  position: relative;
}
a {
  color: inherit;
  text-decoration: none;
}
body.blocked {
  overflow-y: hidden;
}
/*==== ANIMATION-ON-SCROLL ========*/
.animated {
  opacity: 0;
  transform: translateY(5rem);
  transition: .5s;
}
.fade-in {
  opacity: 1;
  transform: translateY(0);
}
.delay-2 {
  transition: .8s;
}
.delay-3 {
  transition: 1s;
}
.delay-4 {
  transition: 1.2s;
}
</style>
