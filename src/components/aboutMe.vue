<template>
  <div>
    <v-container style="min-width: 200px; color: #F5F5F5; padding-top: 0; font-family: 'Arimo', sans-serif">
      <v-row>
        <span class="big-text" data-text="Hello! I'm Kerem">
          Hello! I'm <span style="color: #45B1A0;">Kerem</span>
        </span>
      </v-row>
      <v-row><span class="medium-text">I'm the guy who makes your website <span style="color: #45B1A0; font-weight: bold">look</span> and <span style="color: #45B1A0; font-weight: bold">work</span> great.</span></v-row>
      <v-row><span class="small-text">Self-taught and mission-driven, I'm a full-stack developer at <a target="_blank" class="job-link" href="https://genomize.com">Genomize</a>, a startup translating genomic data into meaningful insights. Beyond the backend and frontend, I also delve into web design and cherish moments with my feline friend.</span></v-row>
      <v-row class="flex-nowrap" style="padding-top: 40px" justify="end">
        <v-col cols="2">
          <a target="_blank" href="https://github.com/kcanakdag">
            <div class="svg-icon-github">
              <svg viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg"><path d="M251.008 795.861333c-12.8-8.533333-23.808-19.413333-36.693333-34.816a2146.986667 2146.986667 0 0 1-19.882667-24.704c-19.754667-24.533333-32.213333-35.84-45.098667-40.490666a42.666667 42.666667 0 0 1 28.842667-80.341334c32.085333 11.52 53.802667 31.36 83.072 67.754667-4.010667-4.992 14.506667 18.218667 18.474667 22.997333 8.106667 9.685333 14.08 15.573333 18.773333 18.688 8.704 5.845333 25.045333 8.362667 49.066667 5.973334 0.981333-16.298667 4.010667-32.128 8.618666-46.72C229.546667 653.226667 157.866667 571.562667 157.866667 411.306667c0-52.906667 15.786667-100.522667 45.141333-140.458667-9.301333-38.144-7.893333-84.266667 12.885333-136.192a42.666667 42.666667 0 0 1 26.88-24.832c3.456-1.024 5.418667-1.493333 8.874667-2.005333 34.261333-5.248 82.645333 7.253333 145.706667 46.762666A500.522667 500.522667 0 0 1 512 141.44c38.912 0 77.568 4.437333 114.517333 13.141333 63.018667-39.808 111.488-52.309333 146.005334-46.762666 3.626667 0.554667 6.698667 1.28 9.301333 2.133333a42.666667 42.666667 0 0 1 26.282667 24.746667c20.778667 51.882667 22.186667 98.005333 12.885333 136.106666 29.482667 39.936 45.141333 87.253333 45.141333 140.501334 0 160.298667-71.424 241.706667-198.058666 272.725333 5.333333 17.706667 8.106667 37.504 8.106666 58.88a12820.992 12820.992 0 0 1-0.512 115.882667 42.666667 42.666667 0 0 1-0.810666 83.541333c-48.597333 9.728-84.608-22.698667-84.608-65.066667l0.085333-19.029333 0.213333-30.08c0.213333-30.208 0.298667-57.088 0.298667-85.248 0-29.738667-7.808-49.152-18.133333-58.026667-28.202667-24.32-13.909333-70.613333 23.04-74.752 126.592-14.208 185.045333-63.232 185.045333-198.826666 0-40.746667-13.312-74.410667-38.954667-102.570667a42.666667 42.666667 0 0 1-8.106666-44.586667c7.082667-17.664 10.112-40.832 4.096-68.864l-0.426667 0.128c-20.949333 5.930667-47.36 18.773333-79.274667 40.490667a42.666667 42.666667 0 0 1-35.541333 5.76A410.709333 410.709333 0 0 0 512 226.773333c-37.973333 0-75.605333 5.077333-110.592 14.933334a42.666667 42.666667 0 0 1-35.413333-5.717334c-32.085333-21.632-58.624-34.432-79.701334-40.405333-6.144 27.861333-3.114667 50.944 3.925334 68.565333a42.666667 42.666667 0 0 1-8.064 44.586667C256.682667 336.64 243.2 370.944 243.2 411.306667c0 135.338667 58.496 184.661333 184.405333 198.826666 36.906667 4.138667 51.242667 50.218667 23.210667 74.581334-8.192 7.168-18.304 31.232-18.304 58.197333v134.4c0 42.069333-35.626667 73.6-83.626667 65.194667a42.666667 42.666667 0 0 1-1.706666-83.712v-42.24c-38.826667 2.602667-70.912-3.754667-96.170667-20.693334z"  /></svg>
            </div>
          </a>
        </v-col>
        <v-col cols="2">
          <a target="_blank" href="https://gitlab.com/kcanakdag/">
            <div class="svg-icon svg-icon-gitlab">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-gitlab"><path d="M22.65 14.39L12 22.13 1.35 14.39a.84.84 0 0 1-.3-.94l1.22-3.78 2.44-7.51A.42.42 0 0 1 4.82 2a.43.43 0 0 1 .58 0 .42.42 0 0 1 .11.18l2.44 7.49h8.1l2.44-7.51A.42.42 0 0 1 18.6 2a.43.43 0 0 1 .58 0 .42.42 0 0 1 .11.18l2.44 7.51L23 13.45a.84.84 0 0 1-.35.94z"></path></svg>
            </div>
          </a>
        </v-col>
        <v-col cols="2">
          <a target="_blank" href="https://www.linkedin.com/in/kerem-can-akda%C4%9F-84602a132/">
            <div class="svg-icon-linkedin">
              <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Free 6.1.1 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free (Icons: CC BY 4.0, Fonts: SIL OFL 1.1, Code: MIT License) Copyright 2022 Fonticons, Inc. --><path d="M100.28 448H7.4V148.9h92.88zM53.79 108.1C24.09 108.1 0 83.5 0 53.8a53.79 53.79 0 0 1 107.58 0c0 29.7-24.1 54.3-53.79 54.3zM447.9 448h-92.68V302.4c0-34.7-.7-79.2-48.29-79.2-48.29 0-55.69 37.7-55.69 76.7V448h-92.78V148.9h89.08v40.8h1.3c12.4-23.5 42.69-48.3 87.88-48.3 94 0 111.28 61.9 111.28 142.3V448z"/></svg>
            </div>
          </a>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>


<script>
export default {
  name: 'aboutMe',
  components: {
  },
  data() {
    return {
      currentColor: "red"
    };
  },
}
</script>

<style scoped>

.big-text::after, .big-text::before {
  content: " ";
  position: absolute;
  width: 100%;
  height: 100%;
  opacity: 0.2;
  pointer-events: none;
}

.big-text::after {
  top: -20%;
  left: -20%;
  background-image: linear-gradient(to top, rgba(255, 255, 255, 0.5) 5%, rgba(255, 255, 255, 0) 100%);
  transform: scaleY(-1);
  border-radius: 50px;
}

.big-text::before {
  top: 20%; /* Adjust the top value to position it where you'd like */
  left: 20%;
  background-image: linear-gradient(to top, rgba(0, 255, 60, 0.5) 5%, rgba(0, 255, 255, 0) 100%);
  border-radius: 50px;
}
.svg-icon-github {
  width: min(max(30px, 2vw), 50px);
  fill: #F5F5F5;
  vertical-align: middle;
  overflow: hidden;
  transition: fill 0.5s ease, transform 0.3s ease;
}

.svg-icon-github:hover {
  fill: #45B1A0;
  transform: translateY(-5px);
}


.svg-icon-gitlab {
  width: min(max(28px, 1.8vw), 48px);
  stroke: #F5F5F5;
  vertical-align: middle;
  overflow: hidden;
  transition: stroke 0.5s ease, transform 0.3s ease;
}

.svg-icon-gitlab:hover {
  transform: translateY(-5px);
  stroke: #45B1A0;
}

.svg-icon-linkedin {
  width: min(max(28px, 1.8vw), 48px);
  fill: #F5F5F5;
  vertical-align: middle;
  overflow: hidden;
  transition: fill 0.5s ease, transform 0.3s ease;
}

.svg-icon-linkedin:hover {
  transform: translateY(-5px);
  fill: #45B1A0;
}

.job-link{
  color: #F5F5F5;
  transition: color 0.5s ease;
  text-decoration: none;
}

.job-link {
  position: relative;
  color: #45B1A0;
}

.job-link::after {
  content: '';
  position: absolute;
  width: 0;
  height: 2px;
  background: #45B1A0; /* change the color as needed */
  bottom: 0;
  left: 0;
  transition: width 0.3s ease;
}

.job-link:hover::after {
  width: 100%;
}
</style>