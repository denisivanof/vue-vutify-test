<template>
  <v-card>
    <div class="d-flex justify-center">
      <div style="width: 380px; height: 50px">
        <v-autocomplete
            append-icon="mdi-chevron-down"
            class="rounded"
            background-color="border"
            solo
            flat
            placeholder="Choose exchange"
            v-model="withdrawTab.select1"
            :items="withdraw.items"
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
            placeholder="Choose exchange"
            v-model="withdrawTab.select2"
            :items="withdraw.items"
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
  </v-card>
</template>

<script>
export default {
  name: "WithdrawTab",
  props: ['withdraw'],
  model:{
    prop:'withdraw',
    event: 'withdrawChange'
  },
  computed:{
    withdrawTab: {
      get: function() {
        return this.withdraw
      },
      set: function(value) {
        this.$emit('withdrawChange', value)
      }
    }
  }
}
</script>

<style scoped>

</style>