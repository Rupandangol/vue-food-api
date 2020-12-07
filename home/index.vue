<template>
  <!-- <view class="container">
    <text class="text-color-primary">Home</text>
    <HomeList></HomeList>

    <button
      @press="navigatePress(this.props)"
      title="Learn More"
      color="#841584"
      accessibility-label="Learn more about
    this purple button"
    />
  </view> -->
  <view class="container">
    <HomeCard />
    <HomeList />
  </view>
</template>

<style>
* {
  margin: 0;
  padding: 0;
}

</style>

<script>
import HomeList from "./list";
import HomeCard from "./card";

export default {
  components: {
    HomeList,
    HomeCard,
  },

  methods: {
    navigatePress(props) {
      props.navigation.navigate("Detail");
    },
  },
};
</script>


