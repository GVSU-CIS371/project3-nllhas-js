<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" />
    <ul>
      <li>
        <label> Temperature: </label>
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
        <input type="radio" id="b1" value="0" v-model="base" />
        <label for="b1">Black Tea</label>
        <input type="radio" id="b2" value="1" v-model="base" />
        <label for="b2">Green Tea</label>
        <input type="radio" id="b3" value="2" v-model="base" />
        <label for="b3">Coffee</label>
      </li>
      <li>
        <label> Creamer: </label>
        <input type="radio" id="c1" value="0" v-model="creamer" />
        <label for="c1">No Cream</label>
        <input type="radio" id="c2" value="1" v-model="creamer" />
        <label for="c2">Milk</label>
        <input type="radio" id="c3" value="2" v-model="creamer" />
        <label for="c3">Cream</label>
        <input type="radio" id="c4" value="2" v-model="creamer" />
        <label for="c4">Half & Half</label>
      </li>
      <li>
        <label> Syrup: </label>
        <input type="radio" id="s1" value="0" v-model="syrup" />
        <label for="s1">No Syrup</label>
        <input type="radio" id="s2" value="1" v-model="syrup" />
        <label for="s2">Vanilla</label>
        <input type="radio" id="s3" value="2" v-model="syrup" />
        <label for="s3">Caramel</label>
        <input type="radio" id="s4" value="2" v-model="syrup" />
        <label for="s4">Hazelnut</label>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import Beverage from "./components/Beverage.vue";
import { temps, currentTemp, bases, BaseBeverageType, creamers, CreamerType, syrups, SyrupType } from "./stores/beverage";
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
