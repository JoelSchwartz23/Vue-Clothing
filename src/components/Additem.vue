<template>
  <div class="add-item">
    <form @submit.prevent="addItem">
      <input type="text" placeholder="name" v-model='newItem.name' required>
      <input type="url" placeholder="image" v-model="newItem.img" required>
      <input type="number" placeholder="stock" v-model="newItem.stock" required>
      <button type="submit">Submit</button>
    </form>

  </div>
</template>

<script>
  export default {
    name: 'Add item',
    data() {
      return {
        newItem: {}
      }
    },
    method: {
      addItem() {
        this.items.push(this.newItem)
        this.newItem = {}
      }
    }
  }
</script>

<style>
</style>