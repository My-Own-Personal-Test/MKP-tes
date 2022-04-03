<template>
  <b-container>
    <b-row align-h="center" style="margin-top: 10%">
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
  </b-container>
</template>

<script>
export default {};
</script>

<style scoped>
.card {
  background-color: rgb(0, 183, 255);
  border-radius: 8px;
  box-shadow: 2px 3px 4px #ccc;
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
</style>
