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
        >
          <template v-slot:append>
            <v-btn color="label"
                   elevation="0"
                   min-width="47"
                   width="47"
                   height="32"
                   style="text-transform: none; color: white; font-weight: 700;font-size: 12px;line-height: 16px;"
            >Max</v-btn>
          </template>
        </v-text-field>
      </div>
    </div>
    <div class="d-flex justify-center mt-5">
      <v-btn max-width="378" width="100%" height="50" color="primary"
             style="text-transform: none;font-weight: 700;font-size: 14px;line-height: 19px; color: #FFFFFF;"
      >Withdraw</v-btn>
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