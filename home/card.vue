<template>
  <view class="card-container">
    <view class="card-header-block">
      <view class="card-image">
        <image
          :style="{ width: 100, height: 70, borderRadius: 4 }"
          :source="{
            uri:
              'https://facebook.github.io/react-native/docs/assets/favicon.png',
          }"
        />
      </view>
      <view class="">
        <text class="card-header"> Food of The Day </text>
      </view>
    </view>

    <view class="card-text">
      <text class="card-description">Description</text>
      <view class="card-detail">
        <text>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Illum, dicta?
          Totam consequuntur obcaecati officiis facere deleniti iste
          voluptatibus eaque accusantium delectus consectetur, pariatur beatae
          accusamus cumque quo ratione sapiente laudantium.
        </text>
      </view>
      <view class="see-more">
        <touchable-opacity :on-press="onPressButton">
          <text class="see-more-btn">See More</text>
        </touchable-opacity>
      </view>
    </view>
  </view>
</template>


<script>
export default {
  components: {},

  methods: {
    onPressButton: function () {
      alert("clicked");
    },
  },
};
</script>


<style lang="stylus" scoped>
.card-container {
  width: 100%;
  height: 300;
  padding: 20;
}

.card-header-block {
  display: flex;
  flex-direction: row;
}

.card-header {
  margin-left: 30;
  margin-top: 15;
  font-size: 24;
  font-weight: bold;
}

.card-text {
  margin-top: 5;
  display: flex;
  flex-direction: column;
}

.card-description {
  font-weight: bold;
  margin-bottom: 5;
}

.card-detail {
  background-color: white;
  margin-bottom: 5;
  padding: 5;
}

.card-detail text {
  font-style: italic;
}

.see-more {
  width: 70;
  border-radius: 20;
  background-color: #4CAF50; /* Green */
  color: white;
  padding: 5;
}
</style>
