<template>
  <view class="list">
    <view class="list-search">
      <text-input
        :style="{
          height: 30,
          width: 270,
          borderColor: 'gray',
          borderWidth: 1,
        }"
        v-model="text"
      />
      <view class="search-btn">
        <touchable-opacity :on-press="onPressButton">
          <text>Search</text>
        </touchable-opacity>
      </view>
    </view>
    <view>
      <text class="list-header">List of Food</text>
    </view>

    <view class="list-block">
      <flat-list
        :style="{
          height: 200,
          width: 200,
          overflow: 'hidden',
        }"
        :data="[{ key: 'a' }, { key: 'b' }, { key: '2' }, { key: '3' }]"
      >
        <view render-prop-fn="renderItem">
          <HomeListBlock />
        </view>
      </flat-list>
    </view>
  </view>
</template>

<style>
.list {
  /* background-color: "rgba(255,255,0,0.4)"; */
  width: 100%;
  padding: 20;
}
.list-search {
  display: flex;
  flex-direction: row;
}
.search-btn {
  background-color: #4caf50; /* Green */
  color: white;
  padding: 5;
  margin-left: 5;
}
.list-header {
  margin-top: 5;
  margin-bottom: 5;
  font-weight: bold;
  font-size: 17;
}

.list-block {
  /* background-color: aqua; */
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
import React from "react";
import { Text, Flatlist } from "react-native";
import HomeListBlock from "./listBlock";

export default {
  components: {
    HomeListBlock,
  },
  data: function () {
    return {
      isLoading: "true",
      text: "",
    };
  },
  methods: {
    renderList: function (item) {
      return <Text>{item.item.key}</Text>;
    },
    onPressButton: function () {
      alert("Clicked");
    },
  },
};
</script>
