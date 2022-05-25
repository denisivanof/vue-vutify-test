<template>
  <v-app class="app">
    <v-main>
      <v-dialog v-model="dialog" persistent max-width="780">
        <FundYourAcc/>
      </v-dialog>
    </v-main>
  </v-app>
</template>

<script>
import FundYourAcc from "@/components/FundYourAcc/FundYourAcc";
export default {
  name: 'App',
  components: {FundYourAcc},
  data: () => ({
    dialog: true
  })
};
</script>
<style>
.app{
  font-family: 'Open Sans';
}
</style>