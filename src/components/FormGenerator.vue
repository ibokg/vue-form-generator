<template>
  <div class="form">
    <component
      v-for="(field, index) in schema"
      :key="index"
      :is="field.fieldType"
      :value="formData[field.name]"
      @input="updateForm(field.name, $event)"
      v-bind="field"
      class="form__control"
    >
    </component>
  </div>
</template>

<script>
import NumberInput from '@/components/NumberInput'
import SelectList from '@/components/SelectList'
import TextInput from '@/components/TextInput'

export default {
  name: 'FormGenerator',
  components: {
    NumberInput,
    SelectList,
    TextInput
  },
  props: {
    schema: {
      type: Array,
      required: true
    },
    value: {
      required: true
    }
  },
  data() {
    return {
      formData: this.value || {}
    }
  },
  methods: {
    updateForm(fieldName, value) {
      this.$set(this.formData, fieldName, value)
      this.$emit('input', this.formData)
    }
  }
}
</script>

<style lang="scss" scoped>
.form {
  &__control {
    margin: 16px 0;
  }
}
</style>
