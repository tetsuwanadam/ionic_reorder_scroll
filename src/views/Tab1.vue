<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Reorder scroll test</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Reorder scroll test</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <ion-reorder-group @ionItemReorder="doReorder($event)" disabled="false">
        <ion-item v-for="item of items" :key="item">
          <ion-label>
            Item {{ item }}
          </ion-label>
          <ion-reorder slot="end"></ion-reorder>
        </ion-item>
      </ion-reorder-group>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar } from '@ionic/vue';
import { IonItem, IonLabel, IonReorder, IonReorderGroup } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'Tab1',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonItem,
    IonLabel,
    IonReorder,
    IonReorderGroup,
  },
  setup: function() {
    return {
      doReorder: function(event: CustomEvent) {
        event.detail.complete();
      },
      items: [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19]
    }
  }
});
</script>

<style scoped>
</style>