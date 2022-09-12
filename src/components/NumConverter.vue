<!--
ZCONV by Alexander Abraham, a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--
This section holds the virtual DOM elements
that will appear on our page.
-->
<template>

 <!--Getting user input and storing it in "start".-->
 <input v-model="start" placeholder=""/>

 <!--Button to trigger the "convertNum" function.-->
 <button @click="convertNum">Compute</button>

 <!--Button to change conversion modes.-->
 <button @click="changeMode">Switch Mode</button>

 <!--Displays the active mode.-->
 <p>Mode: {{ mode }}</p>

 <!--Displays the conversion's result.-->
 <p>Result: {{ result }}</p>

</template>

<!--
This section hold the JS we want to use.
-->
<script>

// Importing my Zeppo library.
import zeppo from 'zeppo';

export default {
  
  // Naming the component.
  name: 'NumConverter',

  // Section that holds the stateful data
  // and that Vue manages for us.
  data() {

    // Setting up the stateful data.
    return {

       // Input number by the user.
       start: '',

       // Conversion result.
       result: '',

       // Conversion mode: 'bin' or 'dec'.
       mode: 'bin'
    };
  },

  // The section that holds the methods.
  // Vue, again, handles this for us.
  methods: {

    // The function to change the conversion
    // mode.
    changeMode(){
        if (this.mode === 'bin'){
            this.mode = 'dec';
        }
        else {
            this.mode = 'bin';
        }
    },

    // The function to convert between binary and decimal numbers.
    // "this" refers to the current view model. 
    // (This component and the data it holds.)
    // Most important to insult the user, though.
    convertNum(){
        const insult = 'R.O.F.L.'
        if (this.mode === 'bin'){
            if (zeppo.isBin(this.start) === true){
                this.result = zeppo.binToDec(this.start);
            }
            else {
                this.result = insult;
            }
        }
        else {
            if (zeppo.isInt(this.start) === true){
                this.result = zeppo.decToBin(this.start);
            }
            else {
                this.result = insult;
            }
        }
    }
  }  
}
</script>
