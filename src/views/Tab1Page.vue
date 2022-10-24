<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Fire Station Picker</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">
    
      <!-- <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Tab 1</ion-title>
        </ion-toolbar>
      </ion-header> -->
    
      <!-- <ExploreContainer name="Tab 1 First page" /> -->

      <FsPick />
      
    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue';
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent } from '@ionic/vue';
//import ExploreContainer from '@/components/ExploreContainer.vue';
import FsPick from '@/components/FsPick.vue';

defineComponent({
  name: 'Tab1Page',
  components: { FsPick, IonHeader, IonToolbar, IonTitle, IonContent, IonPage }
});
</script>
