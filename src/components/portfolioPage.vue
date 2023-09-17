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
      <v-row style="height: 40px; padding-left: 4vw; padding-right: 4vw" class="fill-height" align-content="center" justify="space-between">
        <v-col class="observe" cols="6" align-self="center" justify="space-between">
          <div style="text-align: start">
            <v-icon color="#F5F5F5">mdi-account-circle</v-icon>
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
          class="main-section flex-nowrap"
          style="
                    padding-top: 55px;
                    padding-right: clamp(16px, 4vw, 50px);
                    padding-left: clamp(16px, 4vw, 50px);
                    padding-bottom: 45px;">
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
          <div ref="projectsSection">
            <span style="color: #F5F5F5">Projects</span>
          </div>
        </v-col>
      </v-row>

      <v-row class="main-section">
        <v-col class="d-flex align-center justify-center observe">
          <div ref="contactSection">
            <span style="color: #F5F5F5">Contact me</span>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
import AboutMe from "@/components/aboutMe.vue";

export default {
  name: 'PortfolioPage',
  components: {AboutMe },
  data() {
    return {
      isTop: true,
      buttonsCollapse: false,
      drawer: false
    };
  },
  mounted() {
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
  },
  methods: {
    handleScroll() {
      this.isTop = window.pageYOffset === 0;
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
}

.colored-bar {
  background-color: rgba(4, 14, 40, 0.6); /* Semi-transparent black */
  backdrop-filter: blur(10px); /* Apply blur */
}

</style>
