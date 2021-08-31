<script lang="ts">
import axios from 'axios';

export default {
  name: 'Stocks',
  data() {
    return {
      stock: [],
      errors: [],
      selected: '',
    };
  },

  created() {
    axios
      .get(
        'https://financialmodelingprep.com/api/v3/profile/AAPL,NVDA,TSLA,AMD,INTC,MDB,SPCE,V,DAL,DOCU,OKTA,AMZN,PINS,TRIP,GDDY,DIS,MCD,NOK,UPWK,IBM,FB,ZM,OZON,NFLX,EA,HLT,H,CCL?apikey=f9b624109eac48ba5e6ad8bc5cb106b8',
      )
      .then((response) => {
        this.stock = response.data;
        console.log(response.data);
      })
      .catch((e) => {
        this.errors.push = e;
      });
  },
};
</script>

<template>
  <div class="stock">
    <div class="stock-item" v-for="item in stock" :key="item.phone">
      <div class="stock-item__info">
        <div class="stock-item__cover">
          <img :src="item.image" alt="" />
        </div>
        <h3 class="stock-item__title">{{ item.companyName }}</h3>
      </div>
      <span class="stock-item__price">{{ item.price }} $</span>
    </div>
    <h3>Get info</h3>
    <select v-model="selected">
      <option valule="" disabled>Select option</option>
      <option v-for="value in stock" :value="value.description" :key="value.phone">
        {{ value.companyName }}
      </option>
    </select>
    <div class="info">
      {{ selected }}
    </div>
  </div>
</template>
