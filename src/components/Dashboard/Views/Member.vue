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
            <div class="col-md-12 col-sm-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title"><font-awesome-icon :icon="['fas', 'user-plus']"/> Add User</h4>
                    <p class="card-category">Fill this form to add new user for accessing the admin panel.</p>
                    </template>
                    <form>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Full Name"
                                      placeholder="User fullname here"
                                      v-model="addUser.fullname"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Nickname"
                                      placeholder="User nickname here"
                                      v-model="addUser.nickname"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Email"
                                      placeholder="someuser@pucomputnig.org"
                                      v-model="addUser.email"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Password"
                                      placeholder="min. 6 characters"
                                      v-model="addUser.password"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-4">
                                <fg-input type="text"
                                      label="Student ID"
                                      placeholder="00X201X000XX"
                                      v-model="addUser.id"
                                >
                                </fg-input>
                            </div>
                            <div class="col-4">
                                <fg-input type="text"
                                      label="Position"
                                      placeholder="Student Development"
                                      v-model="addUser.position"
                                >
                                </fg-input>
                            </div>
                            <div class="col-4">
                                <fg-input type="text"
                                      label="Phone"
                                      placeholder="08XXXXXXXXXX"
                                      v-model="addUser.phone"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="text-center">
                            <button type="submit" class="btn btn-info btn-fill float-right" @click.prevent="postNewUser">
                            Add User
                            </button>
                        </div>    
                    </form>
                </card>

            </div> 
            <!-- End of Form Income -->

          </div>
      </div>
  </div>
</template>

<script>
import LTable from 'src/components/UIComponents/Table.vue'
import Card from 'src/components/UIComponents/Cards/Card.vue'
const TableColumn = ['ID', 'Name','Position','Email', 'Phone']
const TableData = [
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    position: 'superadmin',
    email: 'iqbal@xoxo.com',
    phone: '081322811010'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    position: 'superadmin',
    email: 'iqbal@xoxo.com',
    phone: '081322811010'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    position: 'superadmin',
    email: 'iqbal@xoxo.com',
    phone: '081322811010'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    position: 'superadmin',
    email: 'iqbal@xoxo.com',
    phone: '081322811010'
  },
  {
    id: '001201500028',
    name: 'Muhammad Iqbal',
    position: 'superadmin',
    email: 'iqbal@xoxo.com',
    phone: '081322811010'
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
        email: "",
        password: "",
        fullname: "",
        nickname: "",
        position: "",
        phone: ""
      }
    }
  },
  methods: {
    postNewUser () {
      alert('Your data: ' + JSON.stringify(this.addUser))
    }
  }
}
</script>

<style>

</style>
