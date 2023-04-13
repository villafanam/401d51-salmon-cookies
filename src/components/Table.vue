<script>
import StoreRow from './StoreRow.vue';


export default {
  // props: ["store"],
  data() {
    return {
      headRW: ["Store", "6:00am", "7:00am", "8:00am", "9:00am", "10:00am", "11:00am", "12:00pm", "1:00pm", "2:00pm", "3:00pm", "4:00pm", "5:00pm", "6:00pm", "7:00pm", "DL Total"],
      store: [
        { name: "Seattle", min: 23, max: 65, avg: 6.3 },
        { name: "Tokyo", min: 3, max: 24, avg: 1.2 },
        { name: "Dubai", min: 11, max: 38, avg: 3.7 },
        { name: "Paris", min: 20, max: 38, avg: 2.3 },
        { name: "Lima", min: 2, max: 16, avg: 4.6 },
      ],
    };
  },
  components: { StoreRow }
}

</script>


<template>
  <table id="cookie-stand">
    <tr>
      <th v-for="element in headRW">{{ element }}</th>
    </tr>
    <StoreRow :store="store" />
  </table>
</template>

<style scoped>
table * {
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

 