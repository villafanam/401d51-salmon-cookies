<script>
import StoreRow from './StoreRow.vue';

// defineProps({
//   msg: {
//     type: String,
//     required: true
//   }

// })

const headRW = ["Store", "6:00am", "7:00am", "8:00am", "9:00am", "10:00am", "11:00am", "12:00pm", "1:00pm", "2:00pm", "3:00pm", "4:00pm", "5:00pm", "6:00pm", "7:00pm", "DL Total"];
const store = [{ name: "Seattle", min: 23, max: 65, avg: 6.3 }, { name: "Richland", min: 23, max: 65, avg: 6.3 }];

export default {
  // props: [headRW, store],
  // setup(props) {
  //   console.log(props.store);
  // },
  data() {
    return {
      headRW: ["Store", "6:00am", "7:00am", "8:00am", "9:00am", "10:00am", "11:00am", "12:00pm", "1:00pm", "2:00pm", "3:00pm", "4:00pm", "5:00pm", "6:00pm", "7:00pm", "DL Total"],
      // columns: new Array(14).fill(""),
      store: [{ name: "Seattle", min: 23, max: 65, avg: 6.3 }, { name: "Richland", min: 23, max: 65, avg: 6.3 }],
      // totalDT: 0,
    };
  },
  // computed: {
  //     getRandomCust: function () {
  //         // let results =[];
  //         for (let i in this.columns) {
  //             this.columns[i] = Math.floor(Math.random() * (this.store.max - this.store.min + 1)) + this.store.min;
  //             this.totalDT += this.columns[i];
  //         }
  //         // return results;
  //     },
  //     // renderData: function (stores) {
  //     //   this.totalDT++;
  //     //   return stores.map(function (store, idx) {
  //     //     return <th>{{ getRandomCust(store.min, store.max) }}</th>;
  //     //   });
  //     // }
  // },
  // components: { StoreRow }
}

</script>



<template>
  <table id="cookie-stand">
    <tr>

      <th v-for="element in headRW">{{ element }}</th>

    </tr>

    <StoreRow :store="store[0]" :headRW="headRW" />

  </table>
</template>
