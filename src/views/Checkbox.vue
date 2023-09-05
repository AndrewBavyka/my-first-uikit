<script setup>
import { ref } from 'vue'
import Checkbox from '@/components/Checkbox/Checkbox.vue';
import CheckboxGroup from '@/components/Checkbox//CheckboxGroup.vue';

const checkboxActive = ref(true);
const checkboxDisabled = ref(true);
const checkboxDisabledChecked = ref(true);

const listOfHeroes = ref([
    { name: 'Spider Man', id: 'heroes-1' },
    { name: 'Iron Man', id: 'heroes-2' },
    { name: 'Batman', id: 'heroes-3' },
    { name: 'Super Girl', id: 'heroes-4' },
    { name: 'Capitan America', id: 'heroes-5' },
]);

const selectedHeroes = ref(['heroes-2', 'heroes-5']);

</script>

<template>
    <h1 class="heading-1">Checkbox</h1>
    <h2 class="heading-2">Checkbox Active</h2>
    <div class="line">
        <Checkbox label="Checkbox Active" id="checkboxActive" name="checkboxActive" value="I Like It!"
            v-model:checked="checkboxActive" />
    </div>

    <h2 class="heading-2">Checkbox Disabled</h2>
    <div class="line">
        <Checkbox 
        label="Checkbox Disabled" 
        id="checkboxDisabled" 
        name="checkboxDisabled" 
        value="I Like It!"
        :disabled="checkboxDisabled" 
        v-model:checked="checkboxDisabledChecked" />
    </div>
    <h2 class="heading-2">Checkbox Group</h2>
    <div class="line line_block">
        <p>Selected Heroes: {{ selectedHeroes }}</p>
        <checkbox-group 
        v-model:value="selectedHeroes" 
        name="heroes" 
        :options="listOfHeroes" />
    </div>
</template>