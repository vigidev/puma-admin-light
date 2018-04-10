<template>
  <div class="content">
      <div class="container-fluid">
          <div class="row">
            <div class="col-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title">Admin Member List</h4>
                    <p class="card-category">Admin member list display list of users that have access to admin panel. There are 3 levels of user: superadmin, admin, and member.</p>
                    </template>
                    <div class="table-responsive">
                    <l-table class="table-hover table-striped"
                            :columns="table.columns"
                            :data="table.data"
                            :option="table.option">
                    </l-table>
                    </div>
                </card>

            </div>
          </div>
          <div class="row">
            <div class="col-md-8 col-sm-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title text-success"><font-awesome-icon :icon="['fas', 'user-plus']"/> Add User</h4>
                    <p class="card-category">Fill this form to add a new computizen data.</p>
                    </template>
                    <form>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Student ID"
                                      placeholder="Student ID Here"
                                      v-model="addUser.id"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Student Name"
                                      placeholder="Student name"
                                      v-model="addUser.fullname"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Birthplace"
                                      placeholder="ex. Cikarang"
                                      v-model="addUser.birthplace"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="date"
                                      label="Birthdate"
                                      v-model="addUser.birthdate"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="number"
                                      label="Batch"
                                      placeholder="2016"
                                      v-model="addUser.batch"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Major"
                                      placeholder="IT"
                                      v-model="addUser.major"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="text-center">
                            <button type="submit" class="btn btn-success btn-fill float-center" @click.prevent="postNewUser">
                            Add User
                            </button>
                        </div>    
                    </form>
                </card>

            </div> 
            <!-- End of Form Add User -->

            <div class="col-md-4 col-sm-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title text-success"><font-awesome-icon :icon="['fas', 'user-plus']"/> Add File</h4>
                    <p class="card-category">Add user from data file. Please upload only <span class="text-danger">.csv</span> file extension!</p>
                    </template>

                    <form>
                        <input id="file" v-on:change="onFileChange" type="file" :class="fileclass">
                        <div class="text-center">
                            <button type="submit" class="btn btn-success btn-fill float-center" @click.prevent="postNewUser">
                            Add User
                            </button>
                        </div> 
                    </form>
                </card>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
import LTable from 'src/components/UIComponents/Table.vue'
import Card from 'src/components/UIComponents/Cards/Card.vue'
const TableColumn = ['ID', 'Name','Batch','Major','Birthplace','Birthdate']
const TableData = [
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    batch: '2015',
    major: 'IT',
    birthplace: 'Bandung',
    birthdate:'mm/dd/yyyy'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    batch: '2015',
    major: 'IT',
    birthplace: 'Bandung',
    birthdate:'mm/dd/yyyy'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    batch: '2015',
    major: 'IT',
    birthplace: 'Bandung',
    birthdate:'mm/dd/yyyy'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    batch: '2015',
    major: 'IT',
    birthplace: 'Bandung',
    birthdate:'mm/dd/yyyy'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    batch: '2015',
    major: 'IT',
    birthplace: 'Bandung',
    birthdate:'mm/dd/yyyy'
  }
]
export default {
  components: {
    LTable,
    Card
  },
  data () {
    return {
      table: {
        columns: [...TableColumn],
        data: [...TableData],
        option: "true"
      },
      addUser:{
        id: "",
        birthdate: "",
        birthplace: "",
        fullname: "",
        batch: "",
        major: ""
      },
      fileclass: "btn btn-warning",
      file: ""
    }
  },
  methods: {
    postNewUser () {
      alert('Your data: ' + JSON.stringify(this.addUser))
    },
    onFileChange(e) {
      var files = e.target.files || e.dataTransfer.files;
      if (!files.length){
        fileclass="btn btn-warning"
      } else {
        fileclass="btn btn-success"
      }
      return;
    }
  }
}
</script>

<style>

</style>
