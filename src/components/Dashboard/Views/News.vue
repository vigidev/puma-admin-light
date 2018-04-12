<template>
  <div class="content">
    <div class="container-fluid">
      <div class="row">
        <div class="col-8">
          <card>
              <template slot="header">
                <h4 class="card-title">News and Event List</h4>
                <p class="card-category">This table show article list about event or news.</p>
              </template>
              <div class="table-responsive">
              <l-table class="table-hover table-striped"
                        :columns="table.column"
                        :data="table.data"
                        :option="table.option">
              </l-table>
              </div>
          </card>
        </div>
        <div class="col-4">
          <card>
            <template slot="header">
                <h4 class="card-title text-success"><font-awesome-icon :icon="['fas','plus-square']"/> Add News</h4>
            </template>
            <div class="container-fluid">
              <div class="row">
                <div class="col-6">
                  <button class="btn btn-primary" v-on:click="addLinkClick">Add using Link</button>
                </div>
                <div>
                  <button class="btn btn-fill btn-primary">Create new</button>
                </div>
              </div>
              <div class="row mt-3" v-show="addLink">
                <form class="col">
                  <div class="row">
                    <div class="col">
                      <fg-input type="text"
                                label="Article Link"
                                placeholder="Link Here">
                      </fg-input>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col">
                      <button type="submit" class="btn btn-fill btn-success float-right">Add</button>
                    </div>
                  </div>
                </form>
              </div>
            </div>
          </card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import LTable from 'src/components/UIComponents/Table.vue'
import Card from 'src/components/UIComponents/Cards/Card.vue'

const tableColumn = ['Date', 'Title', 'Author']
const tableData = [
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  },
  {
    date: 'mm/dd/yyyy',
    title: 'Article Title',
    author: 'god must be true'
  }
]
export default {
  components: {
      Card,
      LTable
  },
  data () {
    return {
      table: {
        column: [...tableColumn],
        data: [...tableData],
        option: "true"
      },
      addLink: false
    }
  },
  methods: {
    addLinkClick: function () {
      this.addLink = !this.addLink
    }
  }
}
</script>

<style>

</style>
