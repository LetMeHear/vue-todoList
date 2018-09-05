<template>
  <div>
    <input id="inputA" type="text" class="inputT" placeholder="Input things that you want to do" v-model="newItem">
    <button v-on:click="addNewItem(newItem)">ADD</button>
    <h2 class="h2center">The things you will to do:</h2>
    <ul class="forSoncenter">
      <li class="forRe" v-for="(item, index) in items" v-bind:key="index">
        {{ item }}
        <span class="remove" v-on:click="handleRemove(index)">X</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
  data () {
    return {
      items: [],
      newItem: ''
    }
  },
  methods: {
    addNewItem (item) {
      this.items.push(this.newItem)
      this.newItem = ''
    },
    handleRemove (index) {
      this.items.splice(index, 1)
    }
  }
}
</script>
<style>
.inputT {
  width: 200px;
}
.forRe {
  width: 295px;
  height: 30px;
  font-size: 20px;
  line-height: 30px;
  font-weight: bold;
  border: 1px solid black;
  text-align: left;
  list-style-type: none;
  background-color: aquamarine;
  margin-bottom: 5px;
  padding-left: 5px;
}
.forSoncenter {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.h2center {
  margin: auto auto;
  padding-top: 20px;
}
.remove {
  font-size: 28px;
  float:right;
  color: red;
  cursor: pointer;
}
</style>
