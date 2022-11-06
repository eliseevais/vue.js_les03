<template>
  <div @click="onBtnClick" class="btn">add new cost +</div>
</template>

<script>
export default {
  name: "AddNewCost",
  methods: {
    onBtnClick() {
      this.$emit('showForm');
    },
  },
};
</script>

<style lang="scss" scoped>
.btn {
  width: 150px;
  background-color: #24aca0;
  border: 1px solid ;
  border-radius: 3px;
  color: white;
  padding: 7px 25px;
  margin: 10px auto 20px;
  cursor: pointer;
  transition: 0.3s;
  text-transform: uppercase;
  &:hover {
    background-color: transparent;
    color: #24aca0;
  }
}
</style>
