<template>
  <view class="container">
    <!-- <app-loading v-if="!isAppReady"> </app-loading> -->
    <app v-if="isAppReady"></app>
    <!-- <text>hello vue</text> -->
  </view>
</template>


<script>
import Vue from 'vue-native-core';
import { StackNavigator } from 'vue-native-router';
import { VueNativeBase } from 'native-base';

import App from '../App.vue';

// registering all native-base components to the global scope of the Vue
Vue.use(VueNativeBase);

export default {
  components: { App },
  data: function() {
    return {
      isAppReady: false
    };
  },
  created: function() {
    this.loadFonts();
  },
  methods: {
    loadFonts: async function() {
      try {
        this.isAppReady = false;
        this.isAppReady = true;
      } catch (error) {
        console.log('some error occured', error);
        this.isAppReady = true;
      }
    }
  }
};
</script>

<style>
.container {
  flex: 1;
}
</style>

