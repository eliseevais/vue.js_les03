<template>
  <div class="payment-content">
    <input placeholder="Payment date" v-model="date" />
    <input placeholder="Payment description" v-model="category" />
    <input placeholder="Payment amount" v-model.number="value" type="number" />
    <button @click="onSaveClick">Add +</button>
  </div>
</template>

<script>
export default {
  name: 'AddPaymentForm',
  data() {
    return {
      date: '',
      category: '',
      value: 0,
    }
  },
  computed: {
    getCurrentDate() {
      const today = new Date()
      const d = today.getDate()
      const m = today.getMonth() + 1
      const y = today.getFullYear()
      return `${d}.${m}.${y}`
    }
  },
  methods: {
    onSaveClick() {
      const data = {
        date: this.date || this.getCurrentDate,
        category: this.category,
        value: +this.value,
      }
      this.$emit('addNewPayment', data)
    }
  }
}
</script>

<style lang="scss" scoped>
.payment-content {
  margin: 10px auto 20px;
}


</style>