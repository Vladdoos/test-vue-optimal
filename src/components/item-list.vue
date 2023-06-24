<template>
  <ul>
    <li>
      <h3>name</h3>
      <h3>value</h3>
    </li>
  </ul>
  <ul>
    <li v-for="item in items" :key="item.id">
      <p>{{ item.name }}</p>
      <p>{{ item.value }}</p>
      <button @click="selectItem(item)">Редактировать</button>
    </li>
  </ul>
</template>

<script>
export default {
  name: "item-list",
  props: ['items'],
  emits: ['select-item'],
  methods: {
    selectItem(item) {
      this.$emit('select-item', item);
    }
  }
}
</script>

<style scoped>
ul{
  display: flex;
  justify-content: center;
  flex-direction: column;
  padding: 0;
}
li {
  list-style-type: none;
  display: flex;
  justify-content: space-around;
  position: relative;
}
button{
  opacity: 0;
  margin-top: 10px;
  background: #4be049;
  border: 1px solid #4be049;
  width: 140px;
  height: 32px;
  border-radius: 10px;
  font-weight: 600;
  font-size: 12px;
  line-height: 15px;
  color: #FFFEFB;
  position: absolute;
  left: 100%;
  top: 0;
  cursor: pointer;
}
button:hover{
  background: #FFFEFB;
  border: 1px solid #4be049;
  color: #4be049;
}
li:hover button{
  opacity: 1;
}
p{
  font-size: 18px;
  width: 35%;
}
</style>
