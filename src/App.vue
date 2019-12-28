<template>
  <div class="container">
    <h1 class="heading">Form Generator</h1>

    <form-generator :schema="schema" v-model="formData" />

    <p class="text">
      Hello {{ formData.title }} {{ formData.firstName }}
      {{ formData.lastName }}, I hear you are {{ formData.age }} years old.
    </p>
  </div>
</template>

<script>
import FormGenerator from '@/components/FormGenerator'

export default {
  name: 'FormGeneratorDemo',
  components: {
    FormGenerator
  },
  data: () => ({
    formData: {
      firstName: 'John'
    },
    schema: [
      {
        fieldType: 'SelectList',
        name: 'title',
        multi: false,
        label: 'Title',
        options: ['', 'Mr', 'Ms', 'Mx', 'Dr', 'Madam', 'Lord']
      },
      {
        fieldType: 'TextInput',
        placeholder: 'First Name',
        label: 'First Name',
        name: 'firstName'
      },
      {
        fieldType: 'TextInput',
        placeholder: 'Last Name',
        label: 'Last Name',
        name: 'lastName'
      },
      {
        fieldType: 'NumberInput',
        placeholder: 'Age',
        name: 'age',
        label: 'Age',
        minValue: 0
      }
    ]
  })
}
</script>

<style lang="scss">
$container-width: 800px;

*, *::after, *::before {
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
}

.container {
  width: 100%;
  max-width: $container-width;
  padding: 0 8px;
  margin: 0 auto;
}

.heading {
  text-align: center;
}

.text {
  font-size: 20px;
}
</style>
