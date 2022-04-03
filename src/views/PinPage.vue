<template>
  <b-container
    style="
      height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: space-around;
    "
  >
    <b-row>
      <b-col>
        <div style="padding-top: 12%">Masukan Kode Akses / Pin Anda</div>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <!-- <PincodeInput
          v-model="code"
          :secure="true"
          :characterPreview="false"
          :length="6"
        /> -->
        <payPassword v-model="code" :length="6" :onlyNumber="false" />
      </b-col>
    </b-row>

    <b-row>
      <b-col cols="12">
        <b-row align-h="center">
          <b-col cols="3">
            <div @click="pin('1')" class="numpad">1</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('2')" class="numpad">2</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('3')" class="numpad">3</div>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-col cols="3">
            <div @click="pin('4')" class="numpad">4</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('5')" class="numpad">5</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('6')" class="numpad">6</div>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-col cols="3">
            <div @click="pin('7')" class="numpad">7</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('8')" class="numpad">8</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('9')" class="numpad">9</div>
          </b-col>
        </b-row>
        <b-row align-h="center">
          <b-col cols="3">
            <div @click="fingerPrint" class="numpad">F</div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('0')" class="numpad">0</div>
          </b-col>
          <b-col cols="3">
            <div @click="del" class="numpad">Del</div>
          </b-col>
        </b-row>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <b-button variant="primary" @click="enter" :disabled="loading"
          >OK</b-button
        >
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import PincodeInput from "vue-pincode-input";
import payPassword from "vue-pay-password";
import "vue-pay-password/dist/vue-pay-password.css";
export default {
  components: { PincodeInput, payPassword },
  data() {
    return {
      code: "",
      loading: false,
    };
  },
  methods: {
    pin(input) {
      this.code = this.code.concat(input);
    },
    fingerPrint() {
      console.log("fp");
    },
    del() {
      let codes = this.code.charAt(this.code.length - 1);
      this.code = this.code.replace(codes, "");
    },
    enter() {
      console.log(this.code);
      this.loading = true;
      setTimeout(() => {
        this.loading = false;
      }, 1000);
    },
  },
};
</script>

<style scoped>
.btn {
  border: none;
  height: 70px;
  width: 80%;
  font-size: 18px;
  border-radius: 8px;
}
.numpad {
  border: 1px solid #ccc;
  border-radius: 6px;
  margin-bottom: 10%;
  padding: 20% 0;
}
.payPassword div.sixDigitPassword {
  background: aqua !important;
}
</style>
