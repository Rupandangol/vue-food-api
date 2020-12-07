<template>
  <view class="list-block">
    <view class="food">
      <view class="food-image">
        <image
          :style="{ width: 40, height: 40, borderRadius: 4 }"
          :source="{
            uri:
              'https://facebook.github.io/react-native/docs/assets/favicon.png',
          }"
        />
      </view>
      <view class="food-name">
        <text :style="{ fontSize: 15, marginTop: 6 }">{{ myItem.name }}</text>
      </view>
    </view>
    <!-- <text class="nutrient" :style="{ fontSize: 15, marginTop: 6 }"
      >{{myItem.food_nutrition[0].nutrition.title}} ({{myItem.food_nutrition[0].amount + ' '+ myItem.food_nutrition[0].unit}})</text> -->
    <view :style="{ fontSize: 10, marginTop: 2 }">
      <touchable-opacity :on-press="onPressButton">
        <text class="learn-more-btn">Learn more </text>
      </touchable-opacity>
    </view>
  </view>
</template>


<style lang="stylus">
.list-block {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-bottom: 8;
}

.food {
  display: flex;
  flex-direction: row;
}

.food-image {
  margin-right: 4;
}

.learn-more-btn {
  background-color: #dfad25;
  color: white;
  padding: 5;
  border-radius: 20;
}
</style>

<script>
export default {
  props: {
    myItem: {
      type: Object,
    },
  },
  components: {},

  methods: {
    onPressButton: function () {
      alert("clicked");
    },
  },
};
</script>
