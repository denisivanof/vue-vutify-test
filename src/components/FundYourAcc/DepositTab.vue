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
            v-model="depositTab.select1"
            :items="deposit.items"
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
            v-model="depositTab.select2"
            :items="deposit.items"
        ></v-autocomplete>
      </div>
    </div>

    <div class="d-flex justify-center" style="margin-top: 37px">
      <v-img  max-height="119"
              max-width="112"
              :src="deposit.qrcode"></v-img>
    </div>

    <div class="d-flex justify-center code-text" style="margin-top: 27px">
      {{deposit.text}}
    </div>
    <div class="d-flex justify-center mt-7">
      <v-btn max-width="378" width="100%" height="50" color="primary"
             style="text-transform: none;font-weight: 700;font-size: 14px;line-height: 19px; color: #FFFFFF;"
      >Copy</v-btn>
    </div>
  </v-card>
</template>

<script>
export default {
  name: "DepositTab",
  props: ['deposit'],
  model:{
    prop:'deposit',
    event: 'depositChange'
  },
  computed:{
    depositTab: {
      get: function() {
        return this.deposit
      },
      set: function(value) {
        this.$emit('depositChange', value)
      }
    }
  }
}
</script>

<style scoped>

</style>