<template>
  <div>
    <span>{{ name }}: {{ count }}</span>
    <button @click="decrement">-</button>
    <button @click="increment">+</button>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "package-counter",
  props: ['name'],
  data() {
    return {count: 0}
  },
  methods: {
    increment() {
      this.count += 1;
    },
    decrement() {
      this.count -= 1;
    }
  }
}
</script>

<style scoped>
button {
  display: inline-block;
  width: 20px;
  height: 20px;
  background-color: #301506;
  color: #fff;
  border: 1px solid #fff;
  border-radius: 10px;
  margin-left: 4px;
}

span {
  /*font-weight: bold;*/
  font-size: 20px;
  margin-right: 4px;
  color: #FFF;
}

div {
  text-align: center;
  padding: 1em;
  border-radius: 3px;
}
</style>