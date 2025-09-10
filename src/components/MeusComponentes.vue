<template>
  <div class="campo-formulario">
    <label :for="id">{{ label }}</label>
    <input
      :id="id"
      :type="type"
      :placeholder="placeholder"
      :value="modelValue"
      @input="$emit('update:modelValue', $event.target.value)"
      :required="required"
      class="campo-input"
    />
  </div>
</template>

<script setup>
import { computed } from 'vue';
const props = defineProps({
  label: { type: String, required: true },
  placeholder: { type: String, default: '' },
  modelValue: { type: String, default: '' },
  type: { type: String, default: 'text' },
  required: { type: Boolean, default: false },
  id: { type: String, default: '' }
});
</script>

<style scoped>
.campo-formulario {
  display: flex;
  flex-direction: column;
  gap: 0.3rem;
}
.campo-formulario label {
  font-weight: 600;
  color: #222;
  font-size: 1.05rem;
}
.campo-input {
  padding: 0.7rem 1rem;
  border: 1.5px solid #cbd5e1;
  border-radius: 7px;
  font-size: 1.08rem;
  outline: none;
  transition: border 0.2s;
  width: 100%;
  box-sizing: border-box;
  background: #f1f5f9;
}
.campo-input:focus {
  border-color: #2563eb;
  background: #fff;
}
</style>