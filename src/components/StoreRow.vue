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
  computed: {
    getRandomCust: function () {
      // console.log('columns:', this.columns);
      let randCus = 0;
      // this.totalDT = 0;
      for (let i in this.columns) {
        randCus = Math.floor(Math.random() * (this.store.max - this.store.min + 1)) + this.store.min;
        this.columns[i] = Math.floor(randCus * this.store.avg);
        this.totalDT += this.columns[i];
        //this.colTotal[i] += this.columns[i];
      }
      // console.log('columns:', this.columns);
    },
  },
  // mounted(){
  //   // console.log('props:-----', this.store);
  //   this.getRandomCust();
  // }
}

</script>

<template>
  {{ getRandomCust }}

  <tr>
    <th>{{ store.name }}</th>
    <td v-for="element in columns">{{ element }}</td>
    <td>{{ totalDT }}</td>
  </tr>
  <!-- <p>{{ this.colTotal }}</p> -->
</template>