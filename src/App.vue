<template>
  <div id="app">
    <div class="wrapper">
      <img class="img-logo" alt="Vue logo" src="./assets/logo2.jpg">
      <header>My personal costs</header>
      <main>
        <AddNewCost @showForm="formToggle"></AddNewCost>
        <AddPaymentForm 
          @addNewPayment="onDataPaymentAdd" 
          @closeForm="formToggle" 
          v-if="isFormActive">
        </AddPaymentForm>
        <PaymentsDisplay :items="paymentsList"></PaymentsDisplay>
      </main>
    </div>
  </div>
</template>

<script>
import AddNewCost from './components/AddNewCost.vue';
import AddPaymentForm from './components/AddPaymentForm.vue';
import PaymentsDisplay from './components/PaymentsDisplay.vue';

export default {
  name: 'App',
  components: {
    AddNewCost,
    AddPaymentForm,
    PaymentsDisplay,    
  },
  data() {
    return {
      paymentsList: [],
      isFormActive: false,
    };
  },
  methods: {
    fetchData() {
      return [
        {date: '28.03.2020', category: 'Food', value: 169},
        {date: '24.03.2020', category: 'Transport', value: 360},
        {date: '24.03.2020', category: 'Sport', value: 532},
        {date: '24.03.2020', category: 'Food', value: 600},
        {date: '24.03.2020', category: 'Entertainment', value: 900},
        {date: '24.03.2020', category: 'Health', value: 732},
        {date: '24.03.2020', category: 'Food', value: 650},
        {date: '24.03.2020', category: 'Transport', value: 174},
        {date: '24.03.2020', category: 'Cloths', value: 1240},
        {date: '24.03.2020', category: 'Food', value: 825},
      ];
    },
    onDataPaymentAdd(data) {
      this.paymentsList.push(data)
    },
    formToggle() {
      this.isFormActive = !this.isFormActive;
    },
  },
  created() {
    this.paymentsList = this.fetchData()
  },
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;  
}
.wrapper {
  // border: 1px solid red;
  width: 1080px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-left: auto;
  margin-right: auto;
}
.img-logo {
  width: 400px;
}
header {
  font-size: 48px;
  margin: 20px 0 10px 0;
}
</style>
