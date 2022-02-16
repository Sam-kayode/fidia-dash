<template>
  <label class="check-container my-0" :class="{indeterminate:indeterminate}">
    <input type="checkbox" checked="checked" />
    <span class="checkmark"></span>
  </label>
</template>

<script>
export default {
  name: 'CheckBox',
  props: {
    indeterminate: {
      type: Boolean,
      default: false,
    },
  },
}
</script>

<style lang="scss">
.check-container {
  position: relative;
  cursor: pointer;
  font-size: 22px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  top: -1px;
  height: 20px;
  width: 20px;
  margin-right: 12px;
}

.check-container input {
  position: absolute;
  opacity: 0;
  cursor: pointer;
  height: 0;
  width: 0;
}

.checkmark {
  position: absolute;
  top: 0;
  left: 0;
  height: 20px;
  width: 20px;
  background-color: #ffffff;
  border: 1px solid #d0d5dd;
  border-radius: 6px;
}

.check-container:hover input ~ .checkmark {
  background-color: #f9f5ff;
  border: 1px solid #7f56d9;
}

.check-container input:checked ~ .checkmark {
  background-color: #f9f5ff;
  border: 1px solid #7f56d9;
}

.checkmark:after {
  content: '';
  position: absolute;
  display: none;
}

.check-container input:checked ~ .checkmark:after {
  display: block;
}

.check-container .checkmark:after {
  left: 7px;
  top: 3px;
  width: 5px;
  height: 10px;
  border: solid #7f56d9;
  border-width: 0 2px 2px 0;
  -webkit-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  transform: rotate(45deg);
}

.indeterminate {
 .checkmark:after {
    left: 7px;
    top: 3px;
    width: 5px;
    height: 10px;
    border: solid #7f56d9;
    border-width: 0 2px 0 0;
    -webkit-transform: rotate(90deg);
    -ms-transform: rotate(90deg);
    transform:rotate(90deg);
  }
}
</style>
