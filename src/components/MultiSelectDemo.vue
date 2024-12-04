// src/components/MultiSelectDemo.vue
<template>
  <div class="demo-container">
    <h2>Vue Multiselect Demo</h2>

    <div class="select-container">
      <h3>Single Select</h3>
      <multiselect
              v-model="selectedOption"
              :options="options"
              :searchable="true"
              :close-on-select="true"
              placeholder="Select one"
      />
      <div class="value-display">Selected: {{ selectedOption }}</div>
    </div>

    <div class="select-container">
      <h3>Multiple Select</h3>
      <multiselect
              v-model="selectedOptions"
              :options="options"
              :multiple="true"
              :searchable="true"
              :close-on-select="false"
              placeholder="Select multiple"
      />
      <div class="value-display">Selected: {{ selectedOptions }}</div>
    </div>

    <div class="select-container">
      <h3>Object Select</h3>
      <multiselect
              v-model="selectedObject"
              :options="objectOptions"
              track-by="id"
              label="name"
              placeholder="Select object"
      />
      <div class="value-display">Selected: {{ selectedObject }}</div>
    </div>
  </div>
</template>

<script>
import Multiselect from 'vue-multiselect'

export default {
  components: {
    Multiselect
  },
  data() {
    return {
      options: ['Option 1', 'Option 2', 'Option 3', 'Option 4'],
      selectedOption: 'Option 1',
      selectedOptions: ['Option 1', 'Option 2'],
      objectOptions: [
        { id: 1, name: 'Object 1' },
        { id: 2, name: 'Object 2' },
        { id: 3, name: 'Object 3' }
      ],
      selectedObject: { id: 1, name: 'Object 1' }
    }
  }
}
</script>

<style>
@import 'vue-multiselect/dist/vue-multiselect.css';

.demo-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
}

.select-container {
  margin-bottom: 30px;
}

.value-display {
  margin-top: 10px;
  color: #666;
  font-size: 0.9em;
}

h2 {
  color: #2c3e50;
  margin-bottom: 30px;
}

h3 {
  color: #34495e;
  margin-bottom: 15px;
}
</style>