<template>
  <div id="container">
    
    <!-- <strong>{{ name }}</strong> -->
    <!-- <p>Explore <a target="_blank" rel="noopener noreferrer" href="https://ionicframework.com/docs/components">UI Components</a></p> -->


    <!-- First Name: <div id="howdy"><div>000</div></div> <input type="text" id="myText" value="Mickey"><br> -->
    <!-- FS 004 -->

    <ion-card>
  <ion-card-header>
    <ion-card-title id="howdy" @mouseover="fsMouseOver" ><div>000</div></ion-card-title>
    <ion-card-subtitle>Card Subtitle</ion-card-subtitle>
  </ion-card-header>

  <ion-card-content>
    Here's a small text description for the card content. Nothing more, nothing less.
  </ion-card-content>
</ion-card>



  </div>
</template>

<script lang="ts">
import { defineComponent, ionCard, ionCardTitle, ionCardSubtitle, ionCardContent } from "vue";

export default defineComponent({

  name: "ExploreContainer",
  props: {
    name: String,
  },

  components: {ionCard, ionCardTitle, ionCardSubtitle, ionCardContent},

  // on click handler
  
  methods: {
    fsMouseOver(event) {
      console.log("Mouse over");
      undisableTxt();
      //make editable
      //this.$refs.fs004.readonly = false;

      // // `this` inside methods points to the current active instance
      // alert(`Hello ${this.name}!`)
      // // `event` is the native DOM event
      // if (event) {
      //   alert(event.target.tagName)
      // }
    }
  }
});


//bringing in from w3schools

function getValue(){

//get plan div text
var element = document.getElementById("howdy");
var value = element.childNodes[0].innerText;
  
  
  if(value){
    var rtnval = `<input type="text" id="tbox" value="${value}">`;
  }else{
  
  //alert('fast-company');
  
  //get textbox value
  
  var value = document.getElementById("tbox").value;
  
  //if (tbvalue) alert('the value is: ' + tbvalue);    
  
    var rtnval = `<input type="text" id="tbox" value="${value}">`;
  }
  
  //alert('the value is: ' + rtnval);    

  
  return rtnval; 
}


function disableTxt() {
var value = document.getElementById("tbox").value;
//document.getElementById("myText").disabled = true;
document.getElementById("howdy").innerHTML = `<div>${value}</div>`; 
}

function undisableTxt() {
//document.getElementById("myText").disabled = false;
document.getElementById("howdy").innerHTML = getValue();
  
}



</script>

<style scoped>
#container {
  text-align: center;
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  color: #8c8c8c;
  margin: 0;
}

#container a {
  text-decoration: none;
}

/* iOS places the subtitle above the title */
ion-card-header.ios {
  display: flex;
  flex-flow: column-reverse;
}
</style>
