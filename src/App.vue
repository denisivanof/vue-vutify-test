<template>
  <v-app class="app">
    <v-main style="background: #7E7E7E;">
      <FundYourAcc/>
    </v-main>
  </v-app>
</template>

<script>

import FundYourAcc from "@/components/FundYourAcc/FundYourAcc";
export default {
  name: 'App',
  components: {FundYourAcc},

};
</script>
<style>
.app{
  font-family: 'Open Sans';
}
</style>