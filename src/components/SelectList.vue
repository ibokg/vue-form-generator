<template>
  <div class="select">
    <label :for="name" class="select__label">{{ label }}</label>
    <select
      :multiple="multi"
      :value="value"
      :id="name"
      @input="$emit('input', $event.target.value)"
      class="select__field"
    >
      <option v-for="option in options" :key="option">
        {{ option }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'SelectList',
  props: {
    multi: {
      type: Boolean,
      default: false
    },
    options: {
      type: Array,
      default: []
    },
    name: {
      type: String,
      required: true
    },
    label: {
      type: String,
      required: false
    },
    value: {
      required: false
    }
  }
}
</script>

<style lang="scss" scoped>
.select {
  &__label {
    display: block;
    padding-bottom: 8px;
    font-size: 18px;
    cursor: pointer;
  }

  &__field {
    width: 100%;
    padding: 5px;
    font-size: 16px;
    border: 1px solid #000;
    border-radius: 4px;
  }
}
</style>
