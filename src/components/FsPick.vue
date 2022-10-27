<template>
  <ion-header>

  </ion-header>
  <ion-content class="ion-padding">
    <!-- <ion-button id="open-modal_">FS</ion-button> -->
    <ion-item>
      <ion-label>FS</ion-label>
      <ion-input id="open-modal" ref="output" type="text" placeholder="Fire Station"></ion-input>
    </ion-item>
    <p>{{ message }}</p>
    <ion-modal ref="modal" trigger="open-modal" @load="onLoad" @willDismiss="onWillDismiss">
      <ion-header>
        <ion-toolbar>
          <ion-buttons slot="start">
            <ion-button @click="cancel()">Cancel</ion-button>
          </ion-buttons>
          <!-- <ion-title>Welcome</ion-title> -->
          <ion-buttons slot="end">
            <ion-button :strong="true" @click="confirm()">Confirm</ion-button>
          </ion-buttons>
        </ion-toolbar>
      </ion-header>
      <ion-content class="ion-padding">
        <ion-item>
          <ion-label position="stacked">Enter Fire Station Number</ion-label>
          <ion-input ref="input" type="text" placeholder="Fire Station"></ion-input>
        </ion-item>


        <ion-grid>

          <ion-item>
            <ion-label>Battalions</ion-label>
          </ion-item>

          <ion-row>
            <ion-col>
              <ion-chip @click="stnsel('004'); confirm()" :outline="true">004</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('006'); confirm()" :outline="true">006</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('007'); confirm()" :outline="true">007</ion-chip>
            </ion-col>
          </ion-row>

          <ion-row>
            <ion-col>
              <ion-chip @click="stnsel('012'); confirm()" :outline="true">012</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('017'); confirm()" :outline="true">017</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('019'); confirm()" :outline="true">019</ion-chip>
            </ion-col>
          </ion-row>

          <ion-row>
            <ion-col>
              <ion-chip @click="stnsel('021'); confirm()" :outline="true">021</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('023'); confirm()" :outline="true">023</ion-chip>
            </ion-col>
            <ion-col>
              <ion-chip @click="stnsel('028'); confirm()" :outline="true">028</ion-chip>
            </ion-col>
          </ion-row>

        </ion-grid>



        <!-- listing below -->
        <ion-list>

          <ion-item >
            <ion-label>
              <ion-chip id="i003" class="plist" @click="stnsel('003'); confirm()" :outline="true">003</ion-chip> Pokémon Yellow
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('004'); confirm()" :outline="true">004</ion-chip> Mega Man X
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('007'); confirm()" :outline="true">007</ion-chip> Porsche 911
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('009'); confirm()" :outline="true">009</ion-chip> Audi R8
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('011'); confirm()" :outline="true">011</ion-chip> Dodge Charger
            </ion-label>
          </ion-item>



          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('012'); confirm()" :outline="true">012</ion-chip> Ford Mustang
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('014'); confirm()" :outline="true">014</ion-chip> Dodge Challenger
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('016'); confirm()" :outline="true">016</ion-chip> Audi A5
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('018'); confirm()" :outline="true">018</ion-chip> Jaguar F-Type
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('020'); confirm()" :outline="true">020</ion-chip> Chevrolet Corvette
            </ion-label>
          </ion-item>


          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('022'); confirm()" :outline="true">022</ion-chip> Mazda MX-5 Miata
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('023'); confirm()" :outline="true">023</ion-chip> The Notorious B.I.G.
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('024'); confirm()" :outline="true">024</ion-chip> Jay-Z
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('028'); confirm()" :outline="true">028</ion-chip> Eminem
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('029'); confirm()" :outline="true">029</ion-chip> Rakim
            </ion-label>
          </ion-item>


          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('030'); confirm()" :outline="true">030</ion-chip> Kendrick Lamar
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('032'); confirm()" :outline="true">032</ion-chip> Ghostface Killah
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('033'); confirm()" :outline="true">033</ion-chip> Lauryn Hill
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip class="plist" @click="stnsel('037'); confirm()" :outline="true">037</ion-chip> Andre 3000
            </ion-label>
          </ion-item>
          <ion-item>
            <ion-label>
              <ion-chip display="false" class="plist" @click="stnsel('042'); confirm()" :outline="true">042</ion-chip> Nas
            </ion-label>

          </ion-item>

          <ion-item><br /></ion-item>
          <!--need space-->

        </ion-list>


      </ion-content>
    </ion-modal>
  </ion-content>
</template>
  
<script lang="ts">
import {
  IonButtons,
  IonButton,
  IonModal,
  IonHeader,
  IonContent,
  IonToolbar,
  IonItem,
  IonInput,
  IonLabel,
  IonChip,
  IonCol,
  IonRow,
  IonGrid,
  IonList,
} from '@ionic/vue';
import { OverlayEventDetail } from '@ionic/core/components';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  components: {
    IonButtons,
    IonButton,
    IonModal,
    IonHeader,
    IonContent,
    IonToolbar,
    IonItem,
    IonInput,
    IonLabel,
    IonChip,
    IonCol,
    IonRow,
    IonGrid,
    IonList,
  },
  data() {
    return {
      message: '',
    };
  },
  methods: {
    cancel() {
      (this.$refs.modal as any).$el.dismiss(null, 'cancel');
    },
    confirm() {
      const name = (this.$refs.input as any).$el.value;
      (this.$refs.modal as any).$el.dismiss(name, 'confirm');

    },
    onWillDismiss(ev: CustomEvent<OverlayEventDetail>) {
      if (ev.detail.role === 'confirm') {
        (this.$refs.output as any).$el.value = ev.detail.data;
      }
    },
    onLoad(){
      console.log('onload');
    },
    stnsel(fsnbr: string) {
      (this.$refs.input as any).$el.value = fsnbr;
      this.collectPListItems();
    },

    collectPListItems() {

      let i, a, txtValue, filter;
      const pListElements = document.getElementsByClassName('plist'); //[0]
      
      console.log(pListElements[0].textContent)
      //document.getElementById('i003')!.innerHTML = 'typescipt sucks';


      for (i = 0; i < pListElements.length; i++) {
         a = pListElements[i];
         txtValue = a.textContent;

        filter = (this.$refs.input as any).$el.value.toUpperCase();
         
        //console.log(filter)

             if (txtValue!.toUpperCase().indexOf(filter) > -1) {
             //console.log('-- ' + (pListElements[i] as HTMLElement).style.display);
              //(pListElements[i] as HTMLElement).style.display = '';
              //(document.getElementById('i003') as HTMLDivElement)!.style.display = 'none';

            } else {
              //console.log('++ ' + (pListElements[i] as HTMLElement).style.display);
              //(pListElements[i] as HTMLElement).style.display = 'none';
            }

         //console.log(txtValue);
      }
    },

    // myFunction() {
    //   var input, filter, ul, li, a, i, txtValue;
    //   input = document.getElementById("myInput");
    //   filter = input?.value.toUpperCase();
    //   ul = document.getElementById("myUL");
    //   li = ul.getElementsByTagName("li");

    //   for (i = 0; i < li.length; i++) {
    //     a = li[i].getElementsByTagName("a")[0];
    //     txtValue = a.textContent || a.innerText;
    //     if (txtValue.toUpperCase().indexOf(filter) > -1) {
    //       li[i].style.display = "";
    //     } else {
    //       li[i].style.display = "none";
    //     }
    //   }
    // },

  },
});
</script>