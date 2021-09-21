<template>
  <div class="content">
    <div @click="changeLeft" class="imagePageLeft" alt="Left page logo" />
    <div class="images">
      <div
        @click="callingFunction(image.value)"
        v-for="image in showImages"
        :key="image.id"
        class="cardImage"
        v-bind:style="{ 'background-image': 'url(' + image.src + ')' }"
        :alt="image.alt"
      >
        <div class="backgroundValue" alt="Background value">
          <h5 class="frutigerColor">$ {{ image.value }}</h5>
        </div>
      </div>
    </div>
    <div @click="changeRight" class="imagePageRight" alt="Right page logo" />
  </div>
</template>

<script>
export default {
  name: "Content",
  data() {
    return {
      images: [
        {
          id: 1,
          src: `${require("../../assets/games/donkey_kong_country.jpeg")}`,
          alt: "Donkey Kong",
          value: "98.000",
        },
        {
          id: 2,
          src: `${require("../../assets/games/super_mario.png")}`,
          alt: "Super Mario",
          value: "995.000",
        },
        {
          id: 3,
          src: `${require("../../assets/games/donkey_kong.jpeg")}`,
          alt: "Donkey",
          value: "75.000",
        },
        {
          id: 4,
          src: `${require("../../assets/games/goof_troop.jpeg")}`,
          alt: "goof",
          value: "65.000",
        },
        {
          id: 5,
          src: `${require("../../assets/games/hyrule.png")}`,
          alt: "hyrule",
          value: "22.000",
        },
        {
          id: 6,
          src: `${require("../../assets/games/lol.jpeg")}`,
          alt: "lol",
          value: "55.000",
        },
        {
          id: 7,
          src: `${require("../../assets/games/mario_deluxe.jpeg")}`,
          alt: "Super Mario",
          value: "15.000",
        },
        {
          id: 8,
          src: `${require("../../assets/games/mario_golfo.png")}`,
          alt: "Mario golfo",
          value: "150.000",
        },
        {
          id: 9,
          src: `${require("../../assets/games/mario_kart.jpeg")}`,
          alt: "Mario kart",
          value: "325.000",
        },
        {
          id: 10,
          src: `${require("../../assets/games/mario_party_2.jpeg")}`,
          alt: "mario party",
          value: "75.000",
        },
        {
          id: 11,
          src: `${require("../../assets/games/mario_golfo.png")}`,
          alt: "mario",
          value: "29.000",
        },
        {
          id: 12,
          src: `${require("../../assets/games/goof_troop.jpeg")}`,
          alt: "goof",
          value: "11.000",
        },
        {
          id: 13,
          src: `${require("../../assets/games/yoshi_island.jpeg")}`,
          alt: "yoshi island",
          value: "9.000",
        },
        {
          id: 14,
          src: `${require("../../assets/games/yoshi.jpeg")}`,
          alt: "yoshi",
          value: "35.000",
        },
        {
          id: 15,
          src: `${require("../../assets/games/pokemon.jpeg")}`,
          alt: "pokemon",
          value: "43.000",
        },
        {
          id: 16,
          src: `${require("../../assets/games/yoshi_island.jpeg")}`,
          alt: "yoshi",
          value: "100.000",
        },
        {
          id: 17,
          src: `${require("../../assets/games/yoshi.jpeg")}`,
          alt: "yoshi",
          value: "140.000",
        },{
          id: 18,
          src: `${require("../../assets/games/hyrule.png")}`,
          alt: "hyrule",
          value: "130.000",
        },{
          id: 19,
          src: `${require("../../assets/games/donkey_kong.jpeg")}`,
          alt: "sdonkey",
          value: "120.000",
        },{
          id: 20,
          src: `${require("../../assets/games/super_mario.png")}`,
          alt: "Super Mario",
          value: "111.000",
        },{
          id: 21,
          src: `${require("../../assets/games/pokemon.jpeg")}`,
          alt: "pokemon",
          value: "110.000",
        },{
          id: 22,
          src: `${require("../../assets/games/hyrule.png")}`,
          alt: "hyrule",
          value: "10.000",
        },{
          id: 23,
          src: `${require("../../assets/games/pokemon.jpeg")}`,
          alt: "pokemon",
          value: "100.000",
        },{
          id: 24,
          src: `${require("../../assets/games/donkey_kong.jpeg")}`,
          alt: "donkey",
          value: "100.000",
        },
      ],
      showImages: [],
    };
  },
  mounted: function () {
    this.fillImages();
  },
  methods: {
    fillImages() {
      this.showImages = this.images.slice(0, 8);
    },
    callingFunction(jackpot) {
      this.$emit("changeJackpot", jackpot);
    },
    changeRight() {
      const lastIndex = this.images.findIndex(
        (item) => item.id === this.showImages[this.showImages.length - 1].id
      );
      if (lastIndex !== this.images.length - 1) {
        this.showImages = this.images.slice((lastIndex+1), ((lastIndex+1)+8) > this.images.length - 1 ? this.images.length : ((lastIndex+1)+8));
      }
    },
    changeLeft() {
      const firstIndex = this.images.findIndex(
        (item) => item.id === this.showImages[0].id
      );
      if (firstIndex !== 0) {
        this.showImages = this.images.slice((firstIndex-8), (firstIndex));
      }
    },
  },
};
</script>

<style scoped>
.content {
  flex-grow: 1;
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
  padding: 20px;
}

.imagePageLeft {
  width: 120px;
  height: 120px;
  cursor: pointer;
  transition: filter 0.3s ease-in;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../../assets/images/arrow_left.png");
  padding: 20px;
}

.imagePageLeft:hover {
  filter: brightness(1.2);
}

.imagePageLeft:active {
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../../assets/images/arrow_left.png");
  filter: brightness(2.2);
}

.imagePageRight {
  width: 120px;
  height: 120px;
  cursor: pointer;
  transition: filter 0.3s ease-in;
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../../assets/images/arrow_right.png");
  transition: filter 0.3s ease-in;
  padding: 20px;
}

.imagePageRight:hover {
  filter: brightness(1.2);
}

.imagePageRight:active {
  background-size: cover;
  background-repeat: no-repeat;
  background-image: url("../../assets/images/arrow_right.png");
  filter: brightness(2.2);
}

.images {
  flex-grow: 1;
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-around;
}

.cardImage {
  width: 200px;
  height: 200px;
  margin: 20px;
  margin-top: 0px;
  border-radius: 20px;
  cursor: pointer;
  border: 5px solid #ffe773;
  transition: filter 0.1s ease-in;
  background-repeat: no-repeat;
  background-size: cover;
  justify-content: center;
  display: flex;
  align-items: flex-end;
}

.cardImage:hover {
  filter: brightness(1.2);
}

.backgroundValue {
  width: 60%;
  height: 26px;
  background-size: contain;
  background-repeat: no-repeat;
  background-image: url("../../assets/images/barra_jackpot.png");
  cursor: pointer;
}

.frutigerColor {
  margin: 4px;
  font-size: 20px;
}
</style>