<template>
  <view class="container">
    <text class="text-color-primary">Detail</text>
    <button
      :on-press="navigate"
      title="Learn More"
      color="#841584"
      accessibility-label="Learn more about this purple button"
    />
  </view>
</template>


<script>
export default {
  methods: {
    navigate() {
      alert("yo");
    },
  },
};
</script>
