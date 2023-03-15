<template>
  <div class="counter">
    <button @click="minus" class="minus">-</button>
    <input :value="counter" type="number">
    <button @click="plus" class="plus">+</button>

    <br/>
    <p>Next: </p>{{next + 1}} <br/>
    <p>Prev: </p>{{prev}}
  </div>
</template>

<script>
export default {
  name: "Counter",
  data() {
    return {
      counter: 0,
      next: 0,
      prev: 0
    }
  },

  methods: {
    plus() {
      this.counter++;
    },

    minus() {
      this.counter--;
    }
  },

  watch: {
    counter(newValue, oldValue) {
      this.prev = oldValue;
      this.next = newValue;
    }
  }
}
</script>

<style scoped>

</style>