<template>
  <div>
    <h2>รายละเอียดการจอง</h2>
    <form @submit.prevent="submitReservation">
      <div class="form-group">
        <label for="name">ชื่อ:</label>
        <input type="text" id="name" v-model="reservationData.name" required />
      </div>
      <div class="form-group">
        <label for="datetime">วันและเวลา:</label>
        <input type="datetime-local" id="datetime" v-model="reservationData.datetime" required />
      </div>
      <div class="form-group">
        <label for="email">อีเมล:</label>
        <input type="email" id="email" v-model="reservationData.email" required />
      </div>
      <div class="form-group">
        <label for="phone">เบอร์โทรศัพท์:</label>
        <input type="tel" id="phone" v-model="reservationData.phone" required />
      </div>
      <div class="form-group">
        <label for="quantity">จำนวนโต๊ะ:</label>
        <input type="number" id="quantity" v-model="reservationData.tableCount" required />
      </div>
      <button type="submit">ยืนยันการจอง</button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      reservationData: {
        name: '',
        datetime: '',
        email: '',
        phone: '',
        quantity: '',
      },
    };
  },
  methods: {
    submitReservation() {
      this.$emit('reserve', this.reservationData);
      this.reservationData = {
        name: '',
        datetime: '',
        email: '',
        phone: '',
        quantity: '',
      };
    },
  },
};
</script>

<style scoped>

.form-group {
  margin-bottom: 1rem;
}

label {
  display: block;
}

input[type="text"],
input[type="datetime-local"],
input[type="email"],
input[type="tel"],
input[type="quantity"] {
  width: 100%;
  padding: 0.5rem;
  border: 2px solid #473232;
  border-radius: 4px;
}

button {
  background-color: #6b5b2c; 
  color: #ffffff; 
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
}
</style>
