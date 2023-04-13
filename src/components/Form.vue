<script>
  export default {
    data(){
      return {
        store: 'store',
        min: 0,
        max: 0,
        avg: 1,
      }
    }
  };
</script>

<template>
  <h4>{{ store }} name has min of {{ min }} and max of {{ max }} and avg of {{ avg }} with avg hour sales {{ (Math.floor(Math.random() * (max - min + 1) + min)) * avg }}</h4>
  <form id="city-form">
        <fieldset>
          <legend>City Information</legend>

          <label for="cityName">City Name:</label>
          <input v-model="store" type="text" required="required" id="cityName" name="cityName" placeholder="ex. Seattle">

          <label for="minCus">Minimum Customers #:</label>
          <input v-model="min" type="number" required="required" id="minCus" name="minCus">

          <label for="maxCus">Maximum Customers #:</label>
          <input v-model="max" type="number" required="required" id="maxCus" name="maxCus">

          <label for="avgCSale">Average Cookie Sales</label>
          <input v-model="avg" type="text" required="required" id="avgCSale" name="avgCSale">

        </fieldset>
        <button type="submit">Submit</button>
      </form>
</template>