<template>
  <div class="container">
    <h2>Список элементов:</h2>
    <item-list :items="items" @select-item="selectItem"/>

    <edit-form :selectedItem="selectedItem" :isShowForm="isShowForm" @update-item="updateItem" @close-form="closeForm"/>
  </div>
</template>

<script>
import ItemList from "@/components/item-list.vue";
import EditForm from "@/components/edit-form.vue";

export default {

  name: 'HomeView',
  components: {EditForm, ItemList},
  data() {
    return {
      items: [
        {name: 'foo1', value: 'bar1', id: 0},
        {name: 'foo2', value: 'bar2', id: 1},
        {name: 'foo3', value: 'bar3', id: 2},
        {name: 'foo4', value: 'bar4', id: 3},
        {name: 'foo5', value: 'bar5', id: 4},
        {name: 'foo6', value: 'bar6', id: 5},
        {name: 'foo7', value: 'bar7', id: 6},
        {name: 'foo8', value: 'bar8', id: 7},
        {name: 'foo9', value: 'bar9', id: 8},
        {name: 'foo10', value: 'bar10', id: 9},
        {name: 'foo11', value: 'bar11', id: 10},
        {name: 'foo12', value: 'bar12', id: 11},
        {name: 'foo13', value: 'bar13', id: 12},
        {name: 'foo14', value: 'bar14', id: 13},
        {name: 'foo15', value: 'bar15', id: 14},
        {name: 'foo16', value: 'bar16', id: 15},
        {name: 'foo17', value: 'bar17', id: 16},
        {name: 'foo18', value: 'bar18', id: 17},
        {name: 'foo19', value: 'bar19', id: 18},
        {name: 'foo20', value: 'bar20', id: 19},
        {name: 'foo21', value: 'bar21', id: 20},
        {name: 'foo22', value: 'bar22', id: 21},
        {name: 'foo23', value: 'bar23', id: 22},
        {name: 'foo24', value: 'bar24', id: 23},
        {name: 'foo25', value: 'bar25', id: 24},

      ],
      selectedItem: null,
      isShowForm: false
    };
  },
  methods: {
    closeForm(data) {
      this.isShowForm = data
    },
    selectItem(item) {
      this.selectedItem = item;
      this.isShowForm = true
    },
    updateItem(newValue) {
      if (this.selectedItem) {
        this.selectedItem.value = newValue;
      }
    }
  }
}
</script>

<style scoped>
.container{
  margin: 0 35%;
  max-width: 1900px;
}
</style>
