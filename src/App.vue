<template>
  <div>
    <Beverage 
    :isIced="currentTemp === 'Cold'"
    :base="currentBase" 
    :creamer="currentCreamer" 
    :syrup="currentSyrup" 
    />
    <ul>
      <li>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input 
            type="radio" 
            name="temperature" 
            :id="`r${temp}`" 
            :value="temp" 
            v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>

      <li>
        <label> Base: </label>
        <template v-for="(base, i) in bases" :key="base.id">
          <label>
            <input 
            type="radio" 
            name="base" 
            :id="`b${i}`" 
            :value="base" 
            v-model="currentBase" />
            {{ base.name }}
          </label>
        </template>
      </li>

      <li>
        <template v-for="(creamer, i) in creamers" :key="creamer.id">
          <label>
            <input 
            type="radio" 
            name="creamer" 
            :id="`c${i}`" 
            :value="creamer" 
            v-model="currentCreamer" />
            {{ creamer.name }}
          </label>
        </template>
      </li>

      <li>
        <template v-for="(syrup, i) in syrups" :key="syrup.id">
          <label>
            <input 
            type="radio" 
            name="syrup" 
            :id="`s${i}`" 
            :value="syrup"
             v-model="currentSyrup" />
            {{ syrup.name }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp, bases, creamers, syrups, currentBase, currentCreamer, currentSyrup } from "./stores/beverage";
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>
