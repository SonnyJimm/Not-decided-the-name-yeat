<template>
  <div class="animated fadeIn">
     <div class="container" style="margin-top:40px">
       <form>

  <div class="form-group row">
    <label for="inputName" class="col-sm-2 col-form-label">Name</label>
    <div class="col-sm-10">
      <input type="text" class="form-control" id="inputEmail3" placeholder="Name">
    </div>
  </div>
  
  <div class="form-group row">
    <label for="inputAge" class="col-sm-2 col-form-label">age</label>
    <div class="col-sm-10">
      <input type="number" class="form-control" id="inputage" placeholder="Age">
    </div>
  </div>

  <div class="form-group row">
    <label for="inputphone" class="col-sm-2 col-form-label">Phone Number</label>
      <div class="col-sm-10">
        <input type="number" class="form-control" id="inputphone" placeholder="Phone Number">
      </div>
  </div>

   <div class="form-group row">
      <label for="inputreason" class="col-sm-2 col-form-label">Reason</label>
        <div class="col-sm-10">
          <input type="text" class="form-control" id="inputreason" placeholder="Reason">
        </div>
   </div>

  <div class="form-group row">
    <div class="col-sm-10">
      <button type="submit" class="btn btn-primary">Register</button>
    </div>
  </div>
</form>
     </div>
  </div>
</template>

<script>
import {customerD} from '~/components'
import Table from './base/table.vue'
export default {
  name: 'Register',
  layout: 'example',
  components: {
    customerD,
    Table
  },
  data: function () {
    return {
    }
  },
  methods: {
    
  }
}
</script>