<template>
  <v-app>
    <v-main>
      <portfolioPage></portfolioPage>
    </v-main>
  </v-app>
</template>

<script>

import PortfolioPage from "@/components/portfolioPage.vue";

export default {
  name: 'App',

  components: {
    PortfolioPage
  },

  data: () => ({
    //
  }),
}
</script>
