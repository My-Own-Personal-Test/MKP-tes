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
        <!-- <payPassword v-model="code" :length="6" :onlyNumber="false" /> -->
        <div class="dot-outline">
          <img v-if="!code[0]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[0]" src="../assets/record.png" alt="" />
          <img v-if="!code[1]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[1]" src="../assets/record.png" alt="" />
          <img v-if="!code[2]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[2]" src="../assets/record.png" alt="" />
          <img v-if="!code[3]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[3]" src="../assets/record.png" alt="" />
          <img v-if="!code[4]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[4]" src="../assets/record.png" alt="" />
          <img v-if="!code[5]" src="../assets/circle.png" alt="" />
          <img v-else-if="code[5]" src="../assets/record.png" alt="" />
        </div>
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
            <div @click="fingerPrint" class="finger">
              <img src="../assets/fingerprint.png" alt="" />
            </div>
          </b-col>
          <b-col cols="3">
            <div @click="pin('0')" class="numpad">0</div>
          </b-col>
          <b-col cols="3">
            <div @click="del" class="backspace">
              <b-icon scale="1.5" icon="backspace"></b-icon>
            </div>
          </b-col>
        </b-row>
      </b-col>
    </b-row>

    <b-row>
      <b-col>
        <b-button @click="enter" :disabled="loading">
          <span v-if="!loading">OK</span>
          <b-spinner small v-else></b-spinner>
        </b-button>
      </b-col>
    </b-row>

    <b-modal id="alert" centered>
      <p>Your code is {{ code.join().replace(/[,]/g, "") }}</p>
    </b-modal>
  </b-container>
</template>

<script>
export default {
  data() {
    return {
      code: [],
      loading: false,
    };
  },
  methods: {
    pin(input) {
      this.code.push(input);
    },
    fingerPrint() {
      console.log("fp");
    },
    del() {
      this.code.pop();
    },
    enter() {
      this.$bvModal.show("alert");
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
.dot-outline {
  display: flex;
  justify-content: space-around;
}
.dot-outline img {
  height: 20px;
}
.btn {
  background-color: #00b7ff;
  border: none;
}
.finger {
  padding: 10%;
}
.finger img {
  height: 40px;
}
.backspace {
  padding: 20% 0;
}
</style>
