<template>
  <app-navigator></app-navigator>
</template>

<script>
import { createAppContainer, createStackNavigator } from "vue-native-router";

import Home from "./home";
import Detail from "./detail";

const StackNavigator = createStackNavigator(
  {
    Home: { screen: Home },
    Detail: { screen: Detail },
  },
  {
    initialRouteName: "Home",
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator },
};
</script>