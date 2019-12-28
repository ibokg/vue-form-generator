<template>
  <div class="input">
    <label :for="name" class="input__label">{{ label }}</label>
    <input
      type="text"
      :name="name"
      :value="value"
      :id="name"
      :placeholder="placeholder"
      @input="$emit('input', $event.target.value)"
      class="input__field"
    />
  </div>
</template>

<script>
export default {
  name: 'TextInput',
  props: {
    placeholder: {
      type: String,
      default: ''
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
.input {
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
