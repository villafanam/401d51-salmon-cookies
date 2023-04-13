<script>

export default {
  props: ["store"],
  data() {
    return {
      // headRW: ['Store', '6:00am', '7:00am', '8:00am', '9:00am', '10:00am', '11:00am', '12:00pm', '1:00pm', '2:00pm', '3:00pm', '4:00pm', '5:00pm', '6:00pm', '7:00pm', 'DL Total'],
      // store: [{ name: "Seattle", min: 23, max: 65, avg: 6.3 }, { name: "Richland", min: 23, max: 65, avg: 6.3 }],
      columns: new Array(14).fill(0),
      colTotal: new Array(14).fill(0),
      totalDT: 0,
    }
  },
  methods: {
    getRandomCust: function (storeData) {
      // console.log('columns:', this.columns);
      let randCus = 0;
      this.totalDT = 0;
      for (let i in this.columns) {
        randCus = Math.floor(Math.random() * (storeData.max - storeData.min + 1)) + storeData.min;
        this.columns[i] = Math.floor(randCus * storeData.avg);

        this.totalDT += this.columns[i];
        // console.log('totalDT:--',this.totalDT)
        this.colTotal[i] += this.columns[i];
      }
      // for (let i in this.columns) {
      //   // console.log('colTotal:', this.colTotal);
      //   this.colTotal[i] += this.columns[i];
      // }
    },
  },
  // mounted() {
  //   // console.log('props:-----', this.store);
  //   for (let i in this.store) {
  //     this.getRandomCust(this.store[i]);
  //   }
  // }
}

</script>

<template>
  
  <tr v-for="elm in store">
    {{ getRandomCust(elm) }}
    <th>{{ elm.name }}</th>
    <td v-for="element in columns">{{ element }}</td>
    <td>{{ totalDT }}</td>
  </tr>
  
  <tr>
    <th>Totals</th>
    <td v-for="element in colTotal">{{ element }}</td>
  </tr>
</template>