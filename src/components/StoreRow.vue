<script>

export default {
  props: ["store"],
  data() {
    return {
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

      // filling columns array with data for a city
      for (let i in this.columns) {

        //get random number of customers
        randCus = Math.floor(Math.random() * (storeData.max - storeData.min + 1)) + storeData.min;
        //console.log('randCus: ', randCus);

        // get hourly cookie sales
        this.columns[i] = Math.floor(randCus * storeData.avg);
        //console.log('colums[i]: ', this.columns[i]);

        //daily loacation total 
        this.totalDT += this.columns[i];
        console.log('totalDT:--',this.totalDT)
        this.colTotal[i] += this.columns[i];
        console.log('colTotal[i]:', this.colTotal[i]);

      }
    },
    totalColumns: function (arr) {
      for (let i in arr) {
        // console.log('colTotal:', this.colTotal);
        this.colTotal[i] += arr[i];
      }
    }
  }
}

</script>

<template>
  <!-- <tr v-for="(element,  idx) in store"> -->
  <!-- {{ element.name }} , {{ idx }} -->
  <tr v-for="elm in store">
    {{ getRandomCust(elm) }}
    <!-- {{ totalColumns(columns) }} -->
    <th>{{ elm.name }}</th>
    <!-- <td v-for="(element,  idx) in columns">{{ idx }} </td> -->
    <td v-for="element in columns">{{ element }}</td>
    <td>{{ totalDT }}</td>
  </tr>

  <tr>
    <th>Totals</th>
    <td v-for="element in colTotal">{{ element }}</td>
    <!-- <td v-for="(element,  idx) in colTotal">{{ idx }}</td> -->
  </tr>
</template>

<style scoped>
tr {
  font-family: 'Varela Round', sans-serif;
  border: 1px double #020005;
  padding: 8px;
  color: plum;
}

th {
  font-weight: bold;
  background-color: #501583;
}

td {
  text-align: center;
}
</style>

