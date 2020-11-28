<template>
  <view class="container">
    <text class="text-color-primary">Home</text>
    <button
      @press="navigatePress(this.props)"
      title="Learn More"
      color="#841584"
      accessibility-label="Learn more about
    this purple button"
    />
  </view>
</template>

<script>
export default {
  methods: {
    navigatePress(props) {
      props.navigation.navigate("Detail");
    },
  },
};
</script>
