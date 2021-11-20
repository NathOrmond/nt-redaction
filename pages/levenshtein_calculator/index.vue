<template>
  <div class="flex_container">

    <div class="container_navigation">
      <nav-bar />
    </div>
    <div class="container_body">
      <h1>Levenshtein Distance Calculator</h1>
      <div
      v-if="!display" 
      class="selection_area">

        <div class="selection_area_boxes">

          <div class="selection_box">
            <p>Select First Manuscript:</p>
            <select v-model="mss1Selection">
              <option v-for="(element, index) in availableTexts" v-bind:value="element" :key="index" >
                {{element}}
              </option>
            </select>
          </div>

          <div class="selection_box">
            <p>Select Second Manuscript:</p>
            <select v-model="mss2Selection">
              <option v-for="(element, index) in availableTexts" v-bind:value="element" :key="index" >
                {{element}}
              </option>
            </select>
          </div>

        </div>

        <div class="display_texts">
          <div class="display_text">
            <h4>
              {{mss1Selection}}
            </h4>
            <p>{{mss1Text}}</p>
          </div>
           <div class="display_text">
             <h4>
               {{mss2Selection}}
             </h4>
            <p>{{mss2Text}}</p>
          </div>
        </div>


        <div class="invert_button">
          <button
          v-on:click="invertDisplay"
          >Confirm Selection
          </button>
        </div>
      </div>

      <div
      v-else 
      class="results_area">
        <h2>Table of Calculated Distances</h2>
        <table>
          <tr>
           <th></th>
           <th>{{mss1Selection}}</th>
            <th>{{mss2Selection}}</th>
         </tr>
          <tr>
            <th>{{mss1Selection}}</th>
            <td>{{calculatedResponse.levenshtein.values[mss1Selection][mss1Selection]}}</td>
            <td>{{calculatedResponse.levenshtein.values[mss2Selection][mss1Selection]}}</td>
         </tr>
         <tr>
           <th>{{mss2Selection}}</th>
           <td>{{calculatedResponse.levenshtein.values[mss2Selection][mss1Selection]}}</td>
           <td>{{calculatedResponse.levenshtein.values[mss2Selection][mss2Selection]}}</td>
          </tr>
        </table>

        <div class="display_texts">
          <div class="display_text">
            <h4>
              {{mss1Selection}}
            </h4>
            <p>{{mss1Text}}</p>
          </div>
           <div class="display_text">
             <h4>
               {{mss2Selection}}
             </h4>
            <p>{{mss2Text}}</p>
          </div>
        </div>

        <div class="invert_button">
          <button
          v-on:click="invertDisplay"
          >Run Again</button> 
        </div>
      </div>

    </div>
    <div class="container_footer">
      <pagefooter />
    </div>

  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import NavBar from '~/components/navigation/NavBar.vue';
import Pagefooter from '~/components/footer/Pagefooter.vue';

export default Vue.extend({
  layout: 'default',
  components: {
    NavBar,
    Pagefooter
  },
  data(){
    return{ 
      display : false,
      availableTexts: null, 
      mss1Selection: '',
      mss2Selection: '', 
      mss1Text: '',
      mss2Text: '',
      calculatedResponse: null
     }
  },
  async mounted() {
    this.availableTexts = await this.getAvailableTexts()
  },
  watch: {
    mss1Selection: async function() {
      let response = await fetch(`https://nt-redaction-api.herokuapp.com/display?mss=${this.mss1Selection}`);
      let json = await response.json()
      // console.log(json?.contents)
      this.mss1Text = json?.contents
    }, 
    mss2Selection: async function(newValue, oldValue) {
      let response = await fetch(`https://nt-redaction-api.herokuapp.com/display?mss=${this.mss2Selection}`);
      let json = await response.json()
      // console.log(json?.contents)
      this.mss2Text = json?.contents
    }
  },
  methods: { 
    async invertDisplay(){ 
      if(!this.display){
        // TODO some processing to check valid selection of mss
        let response = await fetch(`https://nt-redaction-api.herokuapp.com/levenshtein?mss1=${this.mss1Selection}&mss2=${this.mss2Selection}`);
        let json = await response.json()
        // console.log(json?.manuscripts)
        this.calculatedResponse = json

        // response = await fetch(`https://nt-redaction-api.herokuapp.com/display?mss=${this.mss1Selection}`);
        // json = await response.json()
        // // console.log(json?.contents)
        // this.mss1Text = json?.contents

        // response = await fetch(`https://nt-redaction-api.herokuapp.com/display?mss=${this.mss2Selection}`);
        // json = await response.json()
        // // console.log(json?.contents)
        // this.mss2Text = json?.contents

        this.display = !this.display
      } else {
        this.calculatedResponse = null
        this.display = !this.display
      }
    },
    async getAvailableTexts() { 
      let response = await fetch("https://nt-redaction-api.herokuapp.com/texts");
      let json = await response.json()
      // console.log(json?.manuscripts)
      return json?.manuscripts
    }, 
    async displayText(mss: string){ 
      let response = await fetch(`https://nt-redaction-api.herokuapp.com/display?mss=${mss}`);
      let json = await response.json()
      // console.log(json?.contents)
      return json?.contents
    }
  }
});
</script>

<style scoped>

table {
  width: 100%;
}

table, th, td {
  border: 2px solid black;
  padding: 2px;
  margin: 5px;
  text-align: center;
  font-size: 14px;
}

tr:hover {
  background-color: lightgray;
}

td:hover {
  background-color: lightgreen;
}

.selection_area{
  justify-content: center;
  align-items: center;
}

.selection_area_boxes{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.selection_box{
  flex-direction: row;
  margin: 5px;
  padding: 2px;
  border: 2px solid black;
}

select{
  padding: 2px;
  margin: 15px;
  width: 90%;
  font-family: inherit;
  font-size: inherit;
  cursor: inherit;
  font-size: 14px;
  line-height: inherit;
}

h1, h2, h3, h4{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.invert_button {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

p {
  padding: 5px;
  margin: 10px;
}

button:hover { 
  background: mediumseagreen;
  box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24), 0 17px 50px 0 rgba(0,0,0,0.19);
}

button { 
  border-radius: 12px;
  padding: 15px;
  margin: 15px;

}

.display_texts{ 
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

.display_text{ 
  border: 2px solid black;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 15px;
  margin: 15px;
}

.flex_container{ 
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center stretch;
  align-content: stretch;
  padding: 0px;
  margin: 0px;
  width: 100%;
  height: 100%;
}

.container_navigation{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 0px;
  margin: 0px;
  width: 100%;
}

.container_body{
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 2%;
  margin: auto;
  width: 100%;
}

.container_footer{
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 1px;
  margin: 1px;
  width: 100%;
}
</style>