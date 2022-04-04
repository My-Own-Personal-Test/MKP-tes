<template>
  <b-container>
    <b-row align-h="center">
      <b-col>
        <b-card>
          <div class="card-head">
            <span>Cari Tempat Wisata</span>
            <div class="icon">
              <b-icon icon="search"></b-icon>
            </div>
          </div>
        </b-card>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <div class="history">
          <span>History Pembelian</span>
        </div>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <div class="destinations">
          <div
            :class="{ provActive: status === 1 }"
            class="prov"
            @click="status = 1"
          >
            All
          </div>
          <div
            :class="{ provActive: status === 2 }"
            class="prov"
            @click="status = 2"
          >
            Jawa Tengah
          </div>
          <div
            :class="{ provActive: status === 3 }"
            class="prov"
            @click="status = 3"
          >
            Jawa Barat
          </div>
          <div
            :class="{ provActive: status === 4 }"
            class="prov"
            @click="status = 4"
          >
            Jawa Timur
          </div>
        </div>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <VueSlickCarousel v-bind="bigCarousel">
          <b-card
            overlay
            class="big-card"
            style="background-color: #fff; border-radius: 8px"
            img-src="https://sikidang.com/wp-content/uploads/Puri-Grand-Maerokoco.jpg"
          >
            <div class="cardSliderBig">
              <b-button>Beli Tiket</b-button>
            </div>
          </b-card>
        </VueSlickCarousel>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <div style="margin-top: 18px; text-align: left">
          <span style="font-weight: 700; font-size: 17px"
            >Destinasi Terbaik</span
          >
        </div>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <VueSlickCarousel v-bind="settings">
          <div v-for="item in cardSlider" :key="item.idx">
            <b-card class="slider-card">
              <div class="image-card">
                <img :src="item.img" alt="" />
              </div>

              <span>{{ item.nama }}</span>
              <br />
              <span style="font-weight: 400">{{ item.desc }}</span>
            </b-card>
          </div>
        </VueSlickCarousel>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <div style="text-align: left; margin-top: 14px">
          <span style="font-weight: 700">Pencarian Terakhir</span>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";

export default {
  components: {
    VueSlickCarousel,
  },
  data() {
    return {
      status: 1,
      settings: {
        dots: false,
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 2,
        slidesToScroll: 1,
        autoplay: true,
        speed: 2000,
      },
      bigCarousel: {
        dots: false,
        dotsClass: "slick-dots custom-dot-class",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 1,
        slidesToScroll: 1,
        autoplay: true,
        speed: 2000,
      },
      cardSlider: [
        {
          img: "https://asset.kompas.com/crops/5fOXY3K4oKdIzs-F7qNcs0qtt68=/0x0:1430x953/750x500/data/photo/2022/01/17/61e57605c2256.jpg",
          nama: "Lawang Sewu",
          desc: " Semarang",
        },
        {
          img: "https://dynamic-media-cdn.tripadvisor.com/media/photo-o/05/ef/47/1c/borobudur-temple.jpg?w=1200&h=1200&s=1",
          nama: "Candi Borobudur",
          desc: "Magelang",
        },
        {
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSlcyW-C-sYE3Nai-y9BbDN4xIYdYcEQ-p18pNb4xgRFxm7xLWLMzwt0-THlARjzuQbELk&usqp=CAU",
          nama: "Sampoo Kong",
          desc: "Semarang",
        },
      ],
    };
  },
};
</script>

<style scoped>
.card {
  background-color: rgb(0, 183, 255);
  border-radius: 8px;
  box-shadow: 2px 3px 4px #ccc;
  margin-top: 10%;
}
.card .card-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.card .card-head .icon {
  background-color: #fff;
  padding: 2% 3.5%;
  border-radius: 4px;
}
.history {
  display: flex;
  justify-content: flex-end;
  margin-top: 6%;
  color: rgb(0, 183, 255);
  text-decoration: underline;
  font-weight: 700;
}
.destinations {
  display: flex;
  align-items: center;
  justify-content: space-around;
  margin-top: 8%;
}
.destinations .prov {
  color: black;
}
.destinations .provActive {
  color: rgb(0, 183, 255);
  text-decoration: underline;
}

.big-card {
  height: 250px;
  background-color: #fff;
  overflow: hidden;
}

.big-card .cardSliderBig {
  height: 250px;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  display: flex;
  align-items: flex-end;
}
.big-card .cardSliderBig .big-img {
  height: 100%;
  overflow: hidden;
  /* display: flex; */
}
.big-card .card-body {
  padding: 0;
}
.big-card .cardSliderBig .btn {
  width: 30%;
  border-radius: 8px;
  background-color: rgb(0, 183, 255);
  border: none;
  margin-bottom: 3%;
  margin-right: 3%;
  z-index: 10;
}
.slider-card {
  background-color: white;
  overflow: hidden;
  width: 85%;
  height: 220px;
  box-shadow: none;
  border-radius: 10px;
}
.slider-card .card-body {
  padding: 6%;
}
.slider-card .card-body .image-card {
  height: 67%;
  display: flex;
  justify-content: center;
  border-radius: 8px;
  overflow: hidden;
}
.slider-card .card-body .image-card img {
  height: 100%;
  width: 100%;
}
.slider-card .card-body .image-card {
  background-color: #ccc;
  margin-bottom: 10px;
}

.slider-card .card-body {
  font-weight: 700;
  text-align: left;
  font-size: 13px;
}
</style>
