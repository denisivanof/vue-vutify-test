<template>
  <v-container class="d-flex align-center justify-center" style="height: 100%">
    <v-card width="780px" height="587px" style="border-radius: 5px;padding: 30px">
      <v-card-title class="pa-0">
        <v-row class="ma-0">
          <v-col class="pa-0" cols="11">
            <v-tabs v-model="tab"
                    slider-size="4"
                    color="dark"
                    height="48"
            >
              <v-tabs-slider></v-tabs-slider>
              <v-tab :class="isTab('deposit')" href="#deposit">Deposit</v-tab>
              <v-tab :class="isTab('withdraw')" href="#withdraw">Withdraw</v-tab>
              <v-tab :class="isTab('rebalance')" href="#rebalance">Rebalance</v-tab>
            </v-tabs>
          </v-col>
          <v-col class="pa-0 d-flex justify-end" cols="1">
            <v-btn small icon>
              <v-icon size="31" color="label">close</v-icon>
            </v-btn>
          </v-col>
        </v-row>
      </v-card-title>

      <v-card-text class="pt-10">
          <v-tabs-items v-model="tab">
            <v-tab-item :value="'deposit'">
              <DepositTab v-model="deposit" />
            </v-tab-item>
            <v-tab-item :value="'withdraw'">
              <WithdrawTab v-model="withdraw"/>
            </v-tab-item>
            <v-tab-item :value="'rebalance'">3333</v-tab-item>
          </v-tabs-items>
      </v-card-text>
    </v-card>
  </v-container>
</template>

<script>

import DepositTab from "@/components/FundYourAcc/DepositTab";
import WithdrawTab from "@/components/FundYourAcc/WithdrawTab";
export default {
  name: "FundYourAcc",
  components: {WithdrawTab, DepositTab},
  data: () => ({
    tab: null,
    deposit:{
      select1: [],
      select2: [],
      items: [
        'Programming',
        'Design',
        'Vue',
        'Vuetify',
      ],
      qrcode: require('../../assets/qrcode.png'),
      text: 'FGBfvcnkfdnvkk74365832ybvcvdfvfvb'
    },
    withdraw:{
      select1: [],
      select2: [],
      items: [
        'Programming',
        'Design',
        'Vue',
        'Vuetify',
      ],
      qrcode: require('../../assets/qrcode.png'),
      text: 'FGBfvcnkfdnvkk74365832ybvcvdfvfvb'
    },

  }),
  methods: {
    isTab(item){
      return item === this.tab ? 'vtab' : 'vtab label--text'
    }
  },
  computed:{
  }
}
</script>

<style scoped>
.code-text{
  margin-top: 27px;
  font-weight: 400;
  font-size: 16px;
  line-height: 22px;
  text-align: center;
  color: #3C484C;

}
.vtab{
  padding: 0;
  margin-right: 40px;
  min-width: 50px;
  letter-spacing: 1px;
  display: block;
  text-transform: none;
  font-weight: 400;
  font-size: 20px;
  line-height: 27px;
}

</style>