<script>
// defineProps({
//   store: {
//     type: Object,
//     required: true
//   },
//   headRW: {
//     type: Array,
//     required: true
//   }
// })

export default {
  props:['store', 'headRW'],
  // setup(props){console.log(test)},
  data() {
    return {
      // headRW: ['Store', '6:00am', '7:00am', '8:00am', '9:00am', '10:00am', '11:00am', '12:00pm', '1:00pm', '2:00pm', '3:00pm', '4:00pm', '5:00pm', '6:00pm', '7:00pm', 'DL Total'],
      columns: new Array(14).fill(''),
      // store:
      // {
      //   name: 'Seattle',
      //   min: 23,
      //   max: 65,
      //   avg: 6.3
      // }
      // ,
      totalDT: 0,
    }
  },
  computed: {
    getRandomCust: function () {
      for (let i in this.columns) {
        this.columns[i] = Math.floor(Math.random() * (this.store.max - this.store.min + 1)) + this.store.min;
        this.totalDT += this.columns[i];
      }
    },
  },
  mounted(){
    this.getRandomCust();
    // console.log('props:-----', props);
  }
}

</script>

<template>
  <!-- {{ getRandomCust }} -->
  <tr>
    <th>{{ store.name }}</th>
    <td v-for="element in columns">
      {{ element }}
    </td>
    <td>{{ totalDT }}</td>
  </tr>
</template>