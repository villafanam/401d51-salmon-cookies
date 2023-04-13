<script>
export default {
  data() {
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
  <h4>{{ store }} name has min of {{ min }} and max of {{ max }} and avg of {{ avg }} with avg hour sales {{
    (Math.floor(Math.random() * (max - min + 1) + min)) * avg }}</h4>
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
    <button @click="submit">Submit</button>
  </form>
</template>

<style>
form {
  font-family: 'Poppins', sans-serif;
  box-sizing: border-box;
  padding: 2rem;
  width: 100%;
  margin: auto;
  margin-top: 4rem;
  border-radius: 1rem;
  /* background-color: #501583; */
  border: 4px solid plum;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  /* grid-template-columns: 1fr 1.25fr; */
}

form legend {
  font-size: 1.5rem;
}

form p {
  font-size: 1rem;
  margin-top: 0.5rem;
}

form label {
  display: inline-block;
  font: 1rem sans-serif;
  margin-top: 0.5rem;
  margin-bottom: 0.5rem;
}

input[type="text"] {
  font-size: 1rem;
  display: block;
  box-sizing: border-box;
  width: 80%;
  padding: 0.5rem 0.75rem;
}

button {
  font-size: 30px;
  width: 30%;
  height: 30%;
  /* margin-top: 1rem; */
  border-radius: 0.25rem;
  cursor: pointer;
  /* padding: 0.75rem 1.25rem; */
  text-align: center;
}


</style>