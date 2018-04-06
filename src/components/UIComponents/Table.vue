<template>
  <table class="table">
    <thead>
      <tr>
        <slot name="columns">
          <th v-for="column in columns">{{column}}</th>
          <th v-show="option" class="col-sm-1">Options</th>
        </slot>
      </tr>
    </thead>
    <tbody>
    <tr v-for="item in data">
      <slot :row="item">
        <td v-for="column in columns" v-if="hasValue(item, column)">{{itemValue(item, column)}}</td>
        <td v-show="option" class="col-sm-1"><a href=""><font-awesome-icon :icon="['far','edit']"/></a>&nbsp;<a href=""><font-awesome-icon :icon="['fas','eraser']"/></a></td>
      </slot>
    </tr>
    </tbody>
  </table>
</template>
<script>
  export default {
    name: 'l-table',
    props: {
      columns: Array,
      data: Array,
      option: Boolean
    },
    data () {
      return {
      }
    },
    methods: {
      hasValue (item, column) {
        return item[column.toLowerCase()] !== 'undefined'
      },
      itemValue (item, column) {
        return item[column.toLowerCase()]
      }
    }
  }
</script>
<style>
</style>
