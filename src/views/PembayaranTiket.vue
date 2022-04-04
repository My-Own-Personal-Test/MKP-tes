<template>
  <b-container>
    <b-row>
      <b-col
        style="
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          min-height: 100vh;
          padding-bottom: 5%;
        "
      >
        <div>
          <b-row>
            <b-col>
              <div class="back-button">
                <b-button @click="$router.go(-1)">
                  <b-icon icon="arrow-left"></b-icon>
                  Back
                </b-button>
              </div>
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <b-card class="card-date">
                <b-icon icon="calendar2-date"></b-icon>
                <span style="margin-left: 10px">{{
                  moment(date).format("LL")
                }}</span>
              </b-card>
              <b-card class="card-edit">
                <span class="edit">Edit</span>
                <span class="delete">Hapus</span>
              </b-card>
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <div class="wisata">
                <span
                  >Objek Wisata {{ $route.params.id.replace("_", " ") }}</span
                >
              </div>
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <div class="rincian">
                <div class="pengunjung">Pengunjung 1</div>
                <div class="tiket">Tiket Masuk</div>
                <div class="detail">
                  <span>Harga Tiket</span>
                  <span>Rp. 10.000</span>
                </div>
                <div class="tiket">Wahana</div>
                <div class="detail">
                  <span>Harga Tiket</span>
                  <span>Rp. 80.000</span>
                </div>
              </div>
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <div class="rincian">
                <div class="pengunjung">Pengunjung2</div>
                <div class="tiket">Wahana</div>
                <div class="detail">
                  <span>Harga Tiket</span>
                  <span>Rp. 100.000</span>
                </div>
              </div>
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <hr />
            </b-col>
          </b-row>

          <b-row>
            <b-col>
              <div class="total">
                <span>Total Pembayaran</span>
                <span>Rp. 190.000</span>
              </div>
            </b-col>
          </b-row>
        </div>

        <div>
          <b-row>
            <b-col>
              <b-card class="continue">
                <span>Rp. 190.000</span>
              </b-card>
              <b-card class="button-next">
                <b-button>Lanjut <b-icon icon="arrow-right"></b-icon></b-button>
              </b-card>
            </b-col>
          </b-row>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import moment from "moment";
moment.locale("id");
export default {
  data() {
    return {
      date: new Date(),
      moment,
      wisata: "",
    };
  },
};
</script>

<style scoped>
.back-button {
  margin-top: 28px;
  display: flex;
  justify-content: flex-start;
}
.back-button .btn {
  background-color: transparent;
  color: rgb(0, 183, 255);
  border: none;
}
.card-date {
  background-color: rgb(0, 183, 255);
  color: #fff;
  border-radius: 8px;
  border: none;
  margin-top: 18px;
  width: 90%;
}
.card-date .card-body {
  display: flex;
  justify-content: flex-start;
}
.card-edit {
  position: absolute;
  top: 30%;
  right: 0;
  left: 55%;
  width: 40%;
  height: 50px;
  margin: auto;
  border-radius: 8px;
}
.card-edit .card-body {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  font-weight: 600;
}

.card-edit .card-body .edit {
  color: rgb(0, 183, 255);
  font-weight: 600;
  text-decoration: underline;
}
.card-edit .card-body .delete {
  color: rgb(255, 47, 0);
  font-weight: 600;
  text-decoration: underline;
}
.wisata {
  display: flex;
  justify-content: flex-start;
  margin: 8% 0;
  font-weight: 600;
}
.rincian {
  padding: 4% 0;
}
.rincian .pengunjung {
  font-weight: 600;
  display: flex;
  justify-content: flex-start;
}
.rincian .tiket {
  display: flex;
  justify-content: flex-start;
}
.rincian .detail {
  display: flex;
  justify-content: space-between;
}
.total {
  display: flex;
  justify-content: space-between;
  font-size: 18px;
  font-weight: 600;
}
.continue {
  background-color: rgb(0, 183, 255);
  border-radius: 10px;
  width: 90%;
  color: #fff;
}
.continue .card-body {
  display: flex;
  justify-content: flex-start;
  font-size: 22px;
  font-weight: 700;
}
.button-next {
  position: absolute;
  top: 0;
  right: 0;
  left: 58%;
  bottom: 3%;
  width: 35%;
  height: 50px;
  margin: auto;
  border-radius: 8px;
}
.button-next .btn {
  background-color: transparent;
  color: rgb(0, 183, 255);
  border: none;
  display: flex;
  align-items: center;
  justify-content: space-between;
  font-weight: 700;
}
.button-next .card-body {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
