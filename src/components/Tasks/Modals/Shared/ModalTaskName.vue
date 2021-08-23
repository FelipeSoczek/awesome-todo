<template>
  <div class="row q-mb-sm">
    <q-input 
      :value="name"
      @input="$emit('update:name', $event)"
      class="col"
      autofocus
      ref="name"
      label="Task Name" 
      outlined 
      :rules="[val => !!val || 'Field is required']"
    >
      <template v-slot:append>
        <q-icon 
          v-if="name"
          @click="$emit('update:name', '')"
          name="close" 
          class="cursor-pointer"
        />  
      </template>
    </q-input>
  </div>
</template>

<script>
export default {
  props: ['name']
}
</script>