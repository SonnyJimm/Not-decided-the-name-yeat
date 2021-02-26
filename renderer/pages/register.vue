<template>
  <div class="animated fadeIn">
     <div class="container" style="margin-top:40px">
  <form>

  <div class="form-group row">
    <label for="inputname" class="col-sm-2 col-form-label">Name</label>
    <div class="col-sm-10">
      <input type="text" class="form-control" id="inputname" placeholder="Name">
    </div>
  </div>
  
  <div class="form-group row">
    <label for="inputage" class="col-sm-2 col-form-label">age</label>
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
      <input type="button" v-on:click="check" class="btn btn-primary" value="Register"/>
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
    check:async function()
    {
      let name = document.getElementById("inputname");
      let age = document.getElementById("inputage");
      let phone_number = document.getElementById("inputphone");
      let reason = document.getElementById("inputreason");
      let result;
      let state=true;
        if(name.value!="")
        {
          name.placeholder="Name";
          name.classList.remove("is-invalid");
        }else
        {
          state=false;
          name.classList.add("is-invalid");
          name.placeholder="This feild cant be empty";
        }
        if(age.value!=""&&age.value>0)
        {
          age.placeholder="Age";
          age.classList.remove("is-invalid");
        }else
        {
          state=false;
          age.classList.add("is-invalid");
          age.placeholder="This feild cant be empty";
        }
        if(phone_number.value!=""&&phone_number.value>0)
        {
          phone_number.placeholder="Phone Number";
          phone_number.classList.remove("is-invalid");
        }else
        {
          state=false;
          phone_number.classList.add("is-invalid");
          phone_number.placeholder="This feild cant be empty";
        }
        if(reason.value!="")
        {
          reason.placeholder="Reason";
          reason.classList.remove("is-invalid");
        }else
        {
          state=false;
          reason.classList.add("is-invalid");
          reason.placeholder="This feild cant be empty";
        }
        if(state == true)
        {
          result = await this.$axios.$post(`http://127.0.0.1:5000/que`,
          {
           
              "name":name.value,
              "age":age.value,
              "reason":reason.value,
              "phone_number":phone_number.value,
              "attemptedTime":Date()
           
          })
        }
        
    },
    sendData: function()
    {
      alert('Sup');
    }
  },
  computed :{
  }
}
</script>