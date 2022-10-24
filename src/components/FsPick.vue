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
      <ion-modal ref="modal" trigger="open-modal" @willDismiss="onWillDismiss">
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
            <ion-label position="stacked">Enter Fire Station Name</ion-label>
            <ion-input ref="input" type="text" placeholder="Fire Station"></ion-input>
          </ion-item>
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
        //IonTitle,
        IonItem,
        IonInput,
        IonLabel,
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
      },
    });
  </script>