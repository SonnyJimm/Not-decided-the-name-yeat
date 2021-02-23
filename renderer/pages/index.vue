<template>
  <div class="animated fadeIn">
     <div class="container">
      <table class="table" >
         <thead>
              <tr>
              <th scope="col">Name</th>
              <th scope="col">Age</th>
              <th scope="col">attemptedTime</th>
              <th scope="col">Phone number</th>
              <th scope="col">Reason</th>
              </tr>
          </thead>
          <tbody>

                <customerD v-for="customer in customers" v-bind:key="customer.id" :name="customer.name" :age="customer.age" :attemptedTime="customer.attemptedTime" 
                :phone_number="customer.phone_number" :reason="customer.reason" />
          </tbody>
     </table>
     </div>
  </div>
</template>

<script>
import {customerD} from '~/components'
import Table from './base/table.vue'
export default {
  name: 'Index',
  layout: 'example',
  components: 
  {
    customerD,
    Table
  },
   async asyncData({$axios}) 
   {
      const customers = await $axios.$get(`http://127.0.0.1:5000/que`,{timeout:2000})
      return {customers}
    },
  data: function () 
  {
    return 
    {
      
    }
  },
  methods: 
  {
  },
  computed: {}
}
</script>