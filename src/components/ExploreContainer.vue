
<template>
  
  
 
  <ion-content class="ion-padding">
    
    <ion-modal ref="modal" trigger="open-modal" @willDismiss="onWillDismiss">
      <ion-header>
        <ion-toolbar>
          <ion-buttons slot="start">
            <ion-button @click="clickme()">Cancel</ion-button>
          </ion-buttons>
          <ion-title>Fire Station Selector</ion-title>
          <ion-buttons slot="end">
            <ion-button :strong="true" @click="confirm()">Confirm</ion-button>
          </ion-buttons>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-item>
          <ion-label position="stacked">Enter Fire Station Number</ion-label>
          <ion-input ref="input" type="text" placeholder="FS#"></ion-input>
        </ion-item>
      </ion-content>
    </ion-modal>
  
  
  </ion-content>
  
  <div id="container">

    <!-- <strong>{{ name }}</strong> -->
    <!-- <p>Explore <a target="_blank" rel="noopener noreferrer" href="https://ionicframework.com/docs/components">UI Components</a></p> -->

    <!-- First Name: <div id="howdy"><div>000</div></div> <input type="text" id="myText" value="Mickey"><br> -->
    <!-- FS 004 -->



    <ion-item>
     
      <ion-label>FS</ion-label>
      <ion-input id="open-modal"></ion-input>
    </ion-item>
    <ion-card>

      <ion-card-header>
        <!-- @mouseover="fsMouseOver" -->
        <ion-card-title id="howdy" @mouseenter="fsMouseEnter" @mouseleave="fsMouseLeave">
        
        </ion-card-title>

 
      </ion-card-header>


    </ion-card>
  </div>
</template>

<script setup lang="ts">
import { defineComponent, ref } from "vue";
import {
  IonButtons,
  IonButton,
  IonModal,
  IonHeader,
  IonContent,
  IonToolbar,
  IonTitle,
  IonItem,
  IonInput,
  IonLabel,
} from '@ionic/vue';
import { OverlayEventDetail } from '@ionic/core/components';
import {
  IonCard,
  IonCardHeader,
  IonCardTitle,
  IonCardSubtitle,

} from "@ionic/vue";
  defineComponent({
  name: "ExploreContainer",
  props: {
    name: String,
  },

  components: {
    IonCard,
    IonCardHeader,
    IonCardTitle,
    IonCardSubtitle,

    //modal-below
    IonButtons,
    IonButton,
    IonModal,
    IonHeader,
    IonContent,
    IonToolbar,
    IonTitle,
    IonItem,
    IonInput,
    IonLabel,
  },
  data() {
    return {
      message: 'This modal example uses triggers to automatically open a modal when the button is clicked.',
    };
  },

  methods: {

    cancel() {
      this.$refs.modal.$el.dismiss(null, 'cancel');
    },
    confirm() {
      const name = this.$refs.input.$el.value;
      this.$refs.modal.$el.dismiss(name, 'confirm');
    },
    onWillDismiss(ev: CustomEvent<OverlayEventDetail>) {
      if (ev.detail.role === 'confirm') {
        this.message = `Hello, ${ev.detail.data}!`;
      }
    },

  // fsMouseEnter: function (event) {
  //   console.log("Mouse Enter");
  //   // undisableTxt();
  //   (document.getElementById("howdy") as HTMLElement).innerHTML = "7"; //getValue();
  // },

  // fsMouseLeave: function (event) {
  //   console.log("Mouse Exit");
  //   //disableTxt();

  //   var value = (document.getElementById("tbox") as HTMLInputElement)?.value;

  //   //  (document.getElementById("howdy") as HTMLElement).innerHTML = `<div>${value}</div>`;
  //   (
  //     document.getElementById("howdy") as HTMLElement
  //   ).innerHTML = `<div>88</div>`;
  // },

  clickme: function () {
    console.log("yeah");
  },
}, //methods

});

//bringing in from w3schools

function getValue() {
  //get plan div text
  var element = document.getElementById("howdy");
  var value = (element?.childNodes[0] as HTMLElement).innerText;
  var rtnval;

  if (value) {
    rtnval = `<input type="text" id="tbox" value="${value}">`;
  } else {
    //alert('fast-company');

    //get textbox value

    //var value = document.getElementById("tbox").value;
    var value2 = (document.getElementById("tbox") as HTMLInputElement).value;

    //if (tbvalue) alert('the value is: ' + tbvalue);

    rtnval = `<input type="text" id="tbox" value="${value2}">`;
  }
}

// function disableTxt() {
//   //var value = document.getElementById("tbox").value;
//   var value = (document.getElementById("tbox") as HTMLInputElement).value;

//   //document.getElementById("myText").disabled = true;
//   (document.getElementById("howdy") as HTMLElement).innerHTML = `<div>${value}</div>`;
//   //(document.getElementById("howdy") as HTMLElement).innerHTML = `<div>3</div>`;

// }

// function undisableTxt() {
//   //document.getElementById("myText").disabled = false;
//   (document.getElementById("howdy") as HTMLElement).innerHTML = getValue();

// }


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
