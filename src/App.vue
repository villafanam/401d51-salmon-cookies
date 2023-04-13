<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
//import runApp  from './components/app.js'
import Form from './components/Form.vue'
import Table from './components/Table.vue'

// const app = createApp(runApp);
// app.mount('#app');
// runApp();
</script>

<template>
  <h1>Cookies</h1>

<!-- <header>
      <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

      <div class="wrapper">
        <HelloWorld msg="You did it!" />
      </div>
    </header> -->

  <main>
    <!-- <TheWelcome /> -->
    <section id="city-sales">
      
      <Form />
      <Table />
      <!-- <form id="city-form">
        <fieldset>
          <legend>City Information</legend>

          <label for="cityName">City Name:</label>
          <input type="text" required="required" id="cityName" name="cityName" placeholder="ex. Seattle">

          <label for="minCus">Minimum Customers #:</label>
          <input type="number" required="required" id="minCus" name="minCus">

          <label for="maxCus">Maximum Customers #:</label>
          <input type="number" required="required" id="maxCus" name="maxCus">

          <label for="avgCSale">Average Cookie Sales</label>
          <input type="text" required="required" id="avgCSale" name="avgCSale">

        </fieldset>
        <button type="submit">Submit</button>
      </form> -->
    
    </section>
  </main>


</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
