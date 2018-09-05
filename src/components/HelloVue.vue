<template>
  <div>
  <p>{{ msg }}</p>
  <button v-on:click="handleAdd">You have click me {{ count }} times.</button>
  <h3>{{ title }}</h3>
  </div>
</template>

<script>
export default {
  name: 'HelloVue',
  data () {
    return {
      msg: 'hahaha',
      title: 'this is a vue app',
      count: 0
    }
  },
  methods: {
    handleAdd () {
      this.count++
      this.title = 'you has clicked the button'
    }
  }
}
</script>
