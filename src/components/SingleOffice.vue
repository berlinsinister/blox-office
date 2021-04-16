<template>
  <div class="single-office-container">
    <div class="container-local link-back">
      <!-- <router-link
        tag="div"
        :to="{ name: 'Office' }"
        class="is-vcenter is-capitalized back-arrow"
      >
        back
      </router-link> -->
      <div class="back-arrow">Back</div>
    </div>

    <div class="container-local title-and-brief-info">
      <div>
        <h1>Hilton Hotel &amp; Residences</h1>
        <div class="brief-info">
          <div class="square-meters">
            Office #12 - 124 m
            <sup>2</sup>
          </div>
          <div class="price">58.000$</div>
        </div>
      </div>
    </div>

    <div v-if="floors > 1" class="container-local project-floors">
      <div>
        <div class="choose-floor">Choose Floor</div>
        <div class="floors">
          <div
            v-for="number in floors"
            :key="number"
            :class="number === activeFloor ? 'active-element' : ''"
            @click="setActiveFloor(number)"
          >
            {{ number }}
          </div>
        </div>
      </div>
    </div>

    <div class="container-local project-plan">
      <img :src="require('../assets/Img/plan.png')" alt="plan" />
    </div>

    <div class="container-local project-details">
      <div>
        <div>
          <p class="project-detail-title">Rental Condensate</p>
          <p>White Frame</p>
        </div>
        <div>
          <p class="project-detail-title">Rental Price</p>
          <label class="toggle">
            <input class="toggle-checkbox" type="checkbox" />
            <div class="toggle-switch rental-price"></div>
            <span class="toggle-label" style="font-weight: bold"
              >1 m <sup>2</sup> - 750 ₾</span
            >
          </label>
        </div>
        <div>
          <p class="project-detail-title">Selling Price</p>
          <label class="toggle">
            <input class="toggle-checkbox" type="checkbox" />
            <div class="toggle-switch selling-price"></div>
            <span class="toggle-label" style="font-weight: bold"
              >$ 12.3334</span
            >
          </label>
        </div>
        <div style="border: none">
          <p class="project-detail-title" style="color: white">Available</p>
        </div>
      </div>
    </div>

    <div class="container-local contact">
      <div>
        <div>
          <i class="fas fa-phone-alt"></i>
          Call
        </div>
        <div>
          <i class="fas fa-calculator"></i>
          Calculator
        </div>
      </div>
    </div>

    <div class="container-local project-description">
      <div>
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quisquam
        accusantium a esse enim doloremque. Quod veritatis enim velit omnis.
        Laudantium, provident culpa. Voluptatibus, porro voluptatem quaerat
        nesciunt pariatur deleniti ad.
      </div>
    </div>

    <div class="container-local polaroids">
      <div>
        <div class="polaroid-card polaroid-1">
          <div class="polaroid-img">
            <img :src="require('../assets/Img/about.png')" alt="polaroid" />
          </div>
          <div class="polaroid-footer"><span>Full Size</span></div>
        </div>
        <div class="polaroid-card polaroid-2">
          <div class="polaroid-img">
            <img :src="require('../assets/Img/about.png')" alt="polaroid" />
          </div>
          <div class="polaroid-footer"><span>Full Size</span></div>
        </div>
        <div class="polaroid-card polaroid-3">
          <div class="polaroid-img">
            <img :src="require('../assets/Img/about.png')" alt="polaroid" />
          </div>
          <div class="polaroid-footer"><span>Full Size</span></div>
        </div>

        <div class="arrow-box">
          <span></span>
          <div class="swiper-button prev"></div>
          <div class="swiper-button next"></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeFloor: 1,
      floors: 4,
    };
  },
  methods: {
    setActiveFloor(number) {
      this.activeFloor = number;
    },
    // toggleHandler() {
    //   console.log("toggle");
    // },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/sass/toggle";
.active-element {
  border: 1px solid #bbc7c4 !important;
  background: #bbc7c4;
  color: white;
}

.single-office-container {
  color: #211c35;
  font-family: "Gotham", sans-serif;
  display: grid;
  grid-template-columns: auto;
  grid-auto-rows: auto;
  justify-content: center;
  grid-gap: 30px;
  // border: 1px solid red;
  margin: 20px 0 50px 0; // new
  .container-local {
    display: flex;
    justify-content: center;
    padding: 0 15px; // new
    // border: 1px dotted royalblue;
    // margin: 30px 0;
    > div {
      // width: 90%;
      width: 100%;
      max-width: 700px;
      // border: 1px dotted gray;
    }
  }
  .back-arrow {
    font-size: 24px;
    cursor: pointer;
    display: inline-flex;
    color: #b69977;
    &::before {
      content: "";
      width: 0;
      height: 0;
      border-style: solid;
      border-width: 10px 14px 10px 0;
      border-color: transparent #b69977 transparent;
      display: block;
      margin-right: 10px;
      margin-top: 3px;
    }
  }
  h1 {
    font-size: 42px;
    font-family: "Adieu", sans-serif;
    text-align: center;
    line-height: 1;
    // padding: 20px 0;
    margin: 20px 0;
  }
  .brief-info {
    font-family: "Adieu", sans-serif;
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    // border: 1px solid green;
    .square-meters {
      font-size: 20px;
    }
    .price {
      font-size: 15px;
      color: #b69977;
    }
  }
  .project-floors {
    font-family: "Adieu", sans-serif;
    .choose-floor {
      text-align: right;
      margin-bottom: 20px;
    }
    .floors {
      display: flex;
      justify-content: space-between;
      > div {
        $size: 50px;
        width: $size;
        height: $size;
        border-radius: 50%;
        border: 1px solid #211c35;
        display: flex;
        justify-content: center;
        align-items: center;
        transition: 0.2s ease-out;
        &:hover {
          cursor: pointer;
          @extend .active-element;
        }
      }
    }
  }
  .project-plan {
    img {
      width: 100%;
      // border: 1px solid red;
      max-width: 500px;
    }
  }
  .project-details {
    > div {
      background: #bbc7c4;
      padding: 10px 25px;
    }
    p {
      line-height: 1.6;
      margin: 0;
    }
    .project-detail-title {
      font-weight: bold;
    }
    > div > div {
      border-bottom: 1px solid white;
      padding: 7px 0;
    }
  }
  .contact {
    > div {
      display: flex;
      justify-content: space-evenly;
      font-family: "Adieu", sans-serif;
    }
    .fas {
      border: 1px solid #211c35;
      padding: 15px;
      margin-right: 10px;
      border-radius: 50%;
      transition: 0.2s ease-out;
      &:hover {
        cursor: pointer;
        @extend .active-element;
      }
    }
  }
  .polaroids {
    // border: 1px solid red;
    $width: 500px;
    $border: 30px;
    > div {
      position: relative;
      // border: 1px solid blue;
      display: flex;
      justify-content: center;
      // height: 100px;
      .polaroid-card {
        max-width: $width;
        width: 100%;
        // border: 1px solid green;
        position: absolute;
        top: 150px;
        .polaroid-img {
          // max-width: $width;
          // width: 100%;
          // border: 1px solid lime;
          display: flex;
          justify-content: center;
          padding-top: 6%;
        }
        img {
          width: 90%;
          max-width: $width - $border * 2;
        }
        .polaroid-footer {
          padding: 8%; // 30px;
          text-align: right;
          font-family: "Adieu", sans-serif;
          span:hover {
            cursor: pointer;
          }
        }
      }
      .polaroid-1 {
        background: #bbc7c4;
        transform: rotate(20deg);
      }
      .polaroid-2 {
        background: #bbc7c4;
        transform: rotate(-20deg);
      }
      .polaroid-3 {
        background: white;
        transform: rotate(-7deg);
        transition: 0.2s ease-out;
        &:hover {
          transform: scale(1.1);
        }
      }
      .arrow-box {
        position: absolute;
        transform: rotate(15deg);
        right: 2%;
        border: 1px solid #b69977;
        border-radius: 100%;
        height: 170px;
        width: 170px;
        &:hover {
          > .prev {
            left: 30px;
          }
          > .next {
            right: 30px;
          }
        }
        span {
          position: absolute;
          content: "";
          height: 1px;
          width: 90%;
          background: #b69977;
          left: 50%;
          top: 50%;
          transform: translate(-50%, -50%) rotate(90deg);
        }
        .swiper-button {
          position: absolute;
          top: 50%;
          transform: translateY(-50%);
          transition: 0.2s ease-out;
          &::after {
            content: "";
            width: 0;
            height: 0;
            border-style: solid;
            border-color: transparent rgba($color: #b69977, $alpha: 0.4)
              transparent;
            display: block;
          }
        }
        .prev {
          left: 40px;
          &::after {
            border-width: 20px 30px 20px 0;
          }
        }
        .next {
          right: 40px;
          &::after {
            border-width: 20px 0 20px 30px;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 768px) {
  .single-office-container h1 {
    font-size: 32px;
    margin: 15px 0;
  }
}
</style>
