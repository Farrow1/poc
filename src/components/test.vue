<template>
    <div class="test">
        <select name="dropdown-1" @change="getS($event)" class="form-control">
            <option>Select</option>
            <option value="Tower 1"> Tower 1 </option>
            <option value="Tower 2"> Tower 2 </option>
            <option value="Tower 3"> Tower 3 </option>
            <option value="Tower 4"> Tower 4 </option>
            <option value="Tower 5"> Tower 5 </option>
        </select>

        
        SSN:<input type="text" id="ssn"><br>
        First Name: <input type="text" id="fname"><br>
        Last Name: <input type="text" id="lname"><br>
    
        <button v-on:click="submit()">submit</button><br><br><br>

        <h3>{{ displayinput }}</h3>
        SSN: <input type="text" readonly id="ssnr"><br>
        First Name: <input type="text" readonly id="fnamer"><br>
        Last Name: <input type="text" readonly id="lnamer"><br>

        <button id="submitback" v-on:click="submitBack()" style="display: none;"> submit</button>

    </div>

    
</template>

<script>
export default {
  name: 'test',
  data() {
      return {
        displayinput : "",
        input :  "",
        ssn : "",
        fname : "",
        lname : ""
      }     
  },
  methods: {
      getS(event) {
          this.input = event.target.value; 
      },
      submit() {
          this.ssn = document.getElementById("ssn").value
          this.fname = document.getElementById("fname").value
          this.lname = document.getElementById("lname").value

          document.getElementById("ssnr").value = this.ssn
          document.getElementById("fnamer").value = this.fname
          document.getElementById("lnamer").value = this.lname
          this.displayinput = this.input

          document.getElementById("submitback").style = ""
      },
      submitBack() {
          
      }
  }

}
</script>
