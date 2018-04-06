<template>
  <div class="content">
      <div class="container-fluid">
          <div class="row">
            <div class="col-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title">PUMA Cash Audit</h4>
                    <p class="card-category">Cash Audit for PUMA Computing Period.</p>
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
            <div class="col-md-6 col-sm-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title">Income Form</h4>
                    <p class="card-category">Please put income here</p>
                    </template>
                    <form>
                        <div class="row">
                            <div class="col-12">
                                <fg-input type="text"
                                      label="Description"
                                      placeholder="Income Description"
                                      v-model="income.description"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="date"
                                      label="Date"
                                      placeholder="ex. 12-Jan-17"
                                      v-model="income.date"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Amount"
                                      placeholder="2000000"
                                      v-model="income.amount"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="text-center">
                            <button type="submit" class="btn btn-info btn-fill float-right" @click.prevent="postIncome">
                            Input Income
                            </button>
                        </div>    
                    </form>
                </card>

            </div> 
            <!-- End of Form Income -->

            <div class="col-md-6 col-sm-12">
                <card>
                    <template slot="header">
                    <h4 class="card-title">Outcome Form</h4>
                    <p class="card-category">Please put outcome here</p>
                    </template>
                    <form>
                        <div class="row">
                            <div class="col-12">
                                <fg-input type="text"
                                      label="Description"
                                      placeholder="Outcome Description"
                                      v-model="outcome.description"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="row">
                            <div class="col-6">
                                <fg-input type="date"
                                      label="Date"
                                      placeholder="ex. 12-Jan-17"
                                      v-model="outcome.date"
                                >
                                </fg-input>
                            </div>
                            <div class="col-6">
                                <fg-input type="text"
                                      label="Amount"
                                      placeholder="2000000"
                                      v-model="outcome.amount"
                                >
                                </fg-input>
                            </div>
                        </div>
                        <div class="text-center">
                            <button type="submit" class="btn btn-info btn-fill float-right" @click.prevent="postIncome">
                            Input Income
                            </button>
                        </div>    
                    </form>
                </card>

            </div>
            <!-- End of Form Outcome -->
          </div>
      </div>
  </div>
</template>

<script>
import LTable from 'src/components/UIComponents/Table.vue'
import Card from 'src/components/UIComponents/Cards/Card.vue'
const TableColumn = ['Date', 'Description','Income','Outcome','Cash']
const TableData = [
  {
    date: '12-Jan-17',
    description: 'Cash from PUMA 2016',
    income: '9.814.200',
    outcome: '',
    cash: '9.814.200',
  },
  {
    date: '13-Jan-17',
    description: 'Cash batch 2016 (Semester 1)',
    income: '3.740.000',
    outcome: '',
    cash: '13.554.200',
  },
  {
    date: '18-Jan-17',
    description: 'Print permission letter for SAP Trial',
    income: '',
    outcome: '8.000',
    cash: '13.546.200',
  },
  {
    date: '19-Jan-17',
    description: 'Basketball',
    income: '',
    outcome: '200.000',
    cash: '13.346.200',
  },
  {
    date: '12-Jan-17',
    description: 'Cash from PUMA 2016',
    income: '9.814.200',
    outcome: '',
    cash: '9.814.200',
  },
  {
    date: '13-Jan-17',
    description: 'Cash batch 2016 (Semester 1)',
    income: '3.740.000',
    outcome: '',
    cash: '13.554.200',
  },
  {
    date: '18-Jan-17',
    description: 'Print permission letter for SAP Trial',
    income: '',
    outcome: '8.000',
    cash: '13.546.200',
  },
  {
    date: '19-Jan-17',
    description: 'Basketball',
    income: '',
    outcome: '200.000',
    cash: '13.346.200',
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
      income:{
        description: "",
        date: "",
        amount: 1000000
      },
      outcome:{
        description: "",
        date: "",
        amount: 3000000
      }
    }
  },
  methods: {
    postIncome () {
      alert('Your data: ' + JSON.stringify(this.income))
    },
    postOutcome () {
      alert('Your data: ' + JSON.stringify(this.outcome))
    }
  }
}
</script>

<style>

</style>
