<template>
  <v-card>
    <div class="d-flex justify-center">
      <div style="width: 380px; height: 76px">
        <div style="height: 16px; margin-bottom: 10px; font-size: 12px;line-height: 16px; padding-left: 12px">Form</div>
        <v-autocomplete
            append-icon="mdi-chevron-down"
            class="rounded"
            background-color="border"
            solo
            flat
            placeholder="Choose exchange"
            v-model="rebalanceTab.select1"
            :items="rebalance.items"
        ></v-autocomplete>
      </div>
    </div>
    <div class="d-flex justify-center mt-5">
      <div style="width: 380px; height: 76px">
        <div style="height: 16px; margin-bottom: 10px; font-size: 12px;line-height: 16px; padding-left: 12px">To</div>
        <v-autocomplete
            append-icon="mdi-chevron-down"
            class="rounded"
            background-color="border"
            solo
            flat
            placeholder="Choose exchange"
            v-model="rebalanceTab.select1"
            :items="rebalance.items"
        ></v-autocomplete>
      </div>
    </div>
    <div class="d-flex justify-center mt-5">
      <div style="width: 380px; height: 50px">
        <v-autocomplete
            class="rounded"
            append-icon="mdi-chevron-down"
            background-color="border"
            solo
            flat
            placeholder="Choose currency"
            v-model="rebalanceTab.select2"
            :items="rebalance.items"
        ></v-autocomplete>
      </div>
    </div>
    <div class="d-flex justify-center mt-5">
        <div style="width: 380px; height: 50px">
          <v-text-field
              solo
              flat
              placeholder="Withdraw amount"
              class="rounded"
              background-color="border"
          ></v-text-field>
        </div>
    </div>
    <div class="d-flex justify-center">
      <div style="width: 380px;">
        <v-card class="pa-5 mb-4"  style="box-shadow: 0 7px 16px rgba(60, 72, 76, 0.1);border-radius: 5px;">
          <div class="d-flex justify-center align-center rounded" style="width: 139px;height: 32px;background: rgba(42, 101, 145, 0.1);color: #2A6591;  font-size: 12px;line-height: 16px;"
          >Balance: <span style="font-weight: 700">{{rebalance.balance}}</span></div>
          <div style="margin-top: 10px">
            <v-btn class="btn" width="45" height="32" min-width="45" elevation="0" color="label">10%</v-btn>
            <v-btn class="btn" width="45" height="32" min-width="45" elevation="0" color="label">25%</v-btn>
            <v-btn class="btn" width="45" height="32" min-width="45" elevation="0" color="label">50%</v-btn>
            <v-btn class="btn" width="52" height="32" min-width="45" elevation="0" color="label">100%</v-btn>
            <v-btn class="btn" width="46" height="32" min-width="45" elevation="0" color="label">Split</v-btn>
          </div>
        </v-card>
      </div>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "RebalanceTab",
  props: ['rebalance'],
  model:{
    prop:'rebalance',
    event: 'rebalanceChange'
  },
  computed:{
    rebalanceTab: {
      get: function() {
        return this.rebalance
      },
      set: function(value) {
        this.$emit('rebalanceChange', value)
      }
    }
  }
}
</script>

<style scoped>
.btn{
  text-transform: none;
  margin-right: 10px;
  font-weight: 700;
  font-size: 12px;
  line-height: 16px;
  color: #FFFFFF;
}
@media (max-width: 438px) {
  .btn{
    margin-bottom: 10px;
  }
}
</style>