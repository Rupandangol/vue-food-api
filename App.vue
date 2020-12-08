<template>
  <app-navigator></app-navigator>
</template>

<script>
import Vue from "vue-native-core";
import { VueNativeBase } from "native-base";
import { createAppContainer, createStackNavigator } from "vue-native-router";

import Home from "./home";
import Detail from "./detail";

// registering all native-base components to the global scope of the Vue
Vue.use(VueNativeBase);

const StackNavigator = createStackNavigator(
  {
    Home: { screen: Home },
    Detail: { screen: Detail },
  },
  {
    initialRouteName: "Home",
    defaultNavigationOptions: {
      headerMode: "none",
      headerVisible: false,
      header: null,
    },
    navigationOptions: {
      headerMode: "none",
      headerVisible: false,
      header: null,
    },
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator },
};
</script>
