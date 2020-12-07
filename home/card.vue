<template>
  <view class="card-container">
    <view class="card-header-block">
      <view v-if="isLoading" :style="{ flex: 1, justifyContent: 'center' }">
        <activity-indicator size="large" color="#0000ff" />
      </view>
      <view class="card-image">
        <image
          :style="{ width: 100, height: 70, borderRadius: 4 }"
          :source="{
            uri: `https://spoonacular.com/cdn/ingredients_100x100/${foodOfTheDay.image}`,
          }"
        />
      </view>
      <view class="">
        <text class="card-header"> {{ foodOfTheDay.name }} </text>
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
  mounted() {
    this.LoadFoodOfTheDay();
  },
  data: function () {
    return {
      api_key:'your api key',
      isLoading: true,
      foodOfTheDay: [],
    };
  },
  methods: {
    onPressButton: function () {
      alert("clicked");
    },

    LoadFoodOfTheDay: function () {
      fetch(
        `http://rest-food-api.herokuapp.com/api/food/brief-paginate/highlight/?page_size=1&secret=${this.api_key}`
      )
        .then((res) => {
          // this.foodOfTheDay= res.json();
          return res.json();
        })
        .then(this.setFoodOfTheDay)
        .catch((err) => {
          console.log(err);
        });
    },
    setFoodOfTheDay(results) {
      this.isLoading=false;
      this.foodOfTheDay = results;
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
