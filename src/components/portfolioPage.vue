<template>
  <v-container class="main-container" fluid>
    <v-app-bar
        fixed
        style="overflow: visible"
        scroll-behavior="hide"
        density="default"
        scroll-threshold="250"
        :flat="isTop"
        class="main-app-bar"
        :class="isTop ? 'transparent-bar' : 'colored-bar'"
    >
      <v-row class="fill-height app-bar-layout" align-content="center" justify="space-between">
        <v-col class="observe" cols="6" align-self="center" justify="space-between">
          <div style="text-align: start">
            <img style="width: 20px; position: relative; top: 5px" src="/favicon.ico" alt="">
            <span class="tag-name pl-3">kcanakdag</span>
          </div>
        </v-col>
        <v-col v-if="!buttonsCollapse" class="observe" cols="6">
          <v-row class="observe" no-gutters justify="end">
            <v-col cols="auto">
              <v-btn v-on:click="scrollTo('homeSection')" flat class="main-toolbar-buttons"><span>Home</span></v-btn>
            </v-col>
            <v-col cols="auto">
              <v-btn v-on:click="scrollTo('projectsSection')" flat class="main-toolbar-buttons"><span>Projects</span></v-btn>
            </v-col>
            <v-col cols="auto">
              <v-btn v-on:click="scrollTo('contactSection')" flat class="main-toolbar-buttons"><span>Contact</span></v-btn>
            </v-col>
          </v-row>
        </v-col>
        <v-app-bar-nav-icon v-else color="white" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

      </v-row>
    </v-app-bar>
    <v-navigation-drawer
        v-model="drawer"
        location="bottom"
        app
        theme="dark"
        class="nav-drawer-portfolio"
        temporary

    >
      <v-list color="transparent">
        <v-list-item style="text-align: center">
          <v-btn v-on:click="scrollTo('homeSection')" flat class="main-toolbar-buttons"><span>Home</span></v-btn>
        </v-list-item>
        <v-list-item style="text-align: center">
          <v-btn v-on:click="scrollTo('aboutSection')" flat class="main-toolbar-buttons"><span>About Me</span></v-btn>
        </v-list-item>
        <v-list-item style="text-align: center">
          <v-btn v-on:click="scrollTo('projectsSection')" flat class="main-toolbar-buttons"><span>Projects</span></v-btn>
        </v-list-item>
        <v-list-item style="text-align: center">
          <v-btn v-on:click="scrollTo('contactSection')" flat class="main-toolbar-buttons"><span>Contact</span></v-btn>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-container fluid>
      <v-row
          justify="space-around"
          align="center"
          class="main-section flex-nowrap">
        <v-col cols="5" class="observe flex-shrink-1">
          <div ref="homeSection">
            <AboutMe></AboutMe>
          </div>
        </v-col>
        <v-col v-if="!buttonsCollapse" cols="auto" class="observe">
          <img style="width: 20vw; min-width: 150px" src="/drawing.png" alt="">
        </v-col>
      </v-row>

      <!--      <v-row class="main-section">-->
      <!--        <v-col class="d-flex align-center justify-center observe">-->
      <!--          <MyIntro></MyIntro>-->
      <!--        </v-col>-->
      <!--      </v-row>-->

      <v-row class="main-section">
        <v-col class="d-flex align-center justify-center observe">
          <div ref="projectsSection blob-section">
            <svg class="blob" id="visual" viewBox="0 0 900 600" width="900" height="600" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
              <g transform="translate(474.3851950778625 354.5365835532206)">
                <path id="blob1" d="M139.8 -202.5C177.7 -164.8 202.5 -119.4 200.8 -76.6C199.1 -33.8 170.9 6.3 148.8 40.3C126.7 74.3 110.6 102.3 86.9 121.6C63.1 140.8 31.5 151.4 -2.2 154.4C-35.9 157.4 -71.7 152.7 -113.9 139.4C-156 126.1 -204.5 104.1 -229.5 65.5C-254.6 26.9 -256.2 -28.4 -234.6 -70.4C-213 -112.5 -168.2 -141.2 -125.2 -177.2C-82.3 -213.3 -41.1 -256.6 4.9 -263.4C50.9 -270.1 101.9 -240.2 139.8 -202.5" fill="#45B1A0"></path>
              </g>
              <g transform="translate(449.22395850975494 307.3212117006764)" style="visibility: hidden;">
                <path id="blob2" d="M120.7 -170.5C158.8 -138.5 193.5 -106.3 212 -65.2C230.5 -24 232.7 26.2 224 79C215.4 131.8 195.9 187.2 156.7 212.5C117.6 237.8 58.8 232.9 14.2 213.4C-30.4 193.8 -60.7 159.6 -84.5 129.3C-108.3 99.1 -125.5 72.7 -154.5 37.4C-183.6 2.2 -224.5 -42 -227.2 -86.3C-230 -130.6 -194.6 -174.9 -150.4 -204.9C-106.2 -234.8 -53.1 -250.4 -5.9 -242.3C41.3 -234.2 82.7 -202.5 120.7 -170.5" fill="#45B1A0"></path>
              </g>
            </svg>
            <span style="color: #F5F5F5">Projects</span>
          </div>
        </v-col>
      </v-row>
      <v-row class="main-section">
        <v-col class="d-flex align-center justify-center observe">
          <div ref="contactSection">
            <contactMe></contactMe>
          </div>
        </v-col>
      </v-row>
    </v-container>
    <div class="fixed-icons">
      <v-divider vertical thickness="30" color="white"></v-divider>
    </div>
  </v-container>
</template>

<script>
import AboutMe from "@/components/aboutMe.vue";
import ContactMe from "@/components/contactMe.vue";
import KUTE from 'kute.js'


export default {
  name: 'PortfolioPage',
  components: {ContactMe, AboutMe },
  data() {
    return {
      isTop: true,
      buttonsCollapse: false,
      drawer: false,
      tween: null
    };
  },
  mounted() {
    this.tween = KUTE.fromTo(
        '#blob1',
        { path: '#blob1' },
        { path: '#blob2' },
        { repeat: 999, duration: 10000, yoyo: true }
    )
    this.tween.start()

    window.addEventListener("scroll", this.handleScroll);

    window.addEventListener('resize', this.setScreenSizeVars);

    this.$nextTick(() => {
      this.observeElements();
    });
  },
  beforeMount() {
    this.setScreenSizeVars()
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
    window.removeEventListener('resize', this.setScreenSizeVars);
    this.tween.stop();
    this.tween = null;
  },
  methods: {
    handleScroll() {
      this.isTop = window.pageYOffset <= 40;
    },
    scrollTo(refName) {
      let block = refName === 'homeSection' ? 'end' : 'center'
      this.$refs[refName].scrollIntoView({ block: block, behavior: 'smooth' });
    },
    setScreenSizeVars() {
      const width = window.innerWidth;
      if (width <= 800) {
        this.buttonsCollapse = true
      } else {
        this.buttonsCollapse = false
        this.drawer = false
      }
    },
    observeElements() {
      const observer = new IntersectionObserver((entries) => {
        let delay = 0;
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            setTimeout(() => {
              entry.target.classList.add('fade-in');
              observer.unobserve(entry.target);
            }, delay);
            delay += 500;
          }
        });
      }, {
        root: null,
        threshold: 0.7
      });

      document.querySelectorAll('.observe').forEach(element => {
        element.style.opacity = 0;
        observer.observe(element);
      });

    }


  }
}
</script>

<style scoped>

.v-col {
  padding: 0;
}
.v-btn {
  font-family: 'Roboto Condensed', sans-serif !important;
  font-weight: 700;  /* Optional; makes text bold */
}

.fade-in {
  animation: fadeIn ease 1s forwards;
}


.main-section {
  height: 90vh;
  padding: 0;
  padding-top: 55px;
  padding-right: clamp(30px, 5vw, 60px);
  padding-left: clamp(30px, 5vw, 60px);
  padding-bottom: 45px;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
    transform: translateY(-50px); /* Starts 50 pixels above the original position */
  }
  100% {
    opacity: 1;
    transform: translateY(0); /* Ends at the original position */
  }
}


/* If scroll is at the top */
.transparent-bar {
  background-color: transparent !important;
}
.main-app-bar {
  transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1)
}
.main-toolbar-buttons {
  color: #F5F5F5;
  transition: color 0.3s ease;
  text-transform: capitalize;
}

.main-toolbar-buttons:hover {
  color: #45B1A0;
}

.tag-name {
  color: #F5F5F5;
  opacity: 0.8;
  font-family: 'Roboto Condensed', sans-serif;
}

.app-bar-layout{
  height: 40px;
  padding-left: 4vw;
  padding-right: 4vw;
}

.colored-bar {
  background-color: rgba(4, 14, 40, 0.6); /* Semi-transparent black */
  backdrop-filter: blur(10px); /* Apply blur */
}

.fixed-icons{

}

.blob-section {
  position: relative;
}

.blob {
  position: absolute;
  scale: 1.5;
  top: 0;
  left: 0;
  z-index: -1;
}


</style>
