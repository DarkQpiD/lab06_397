<template>
  <div>
    <h1>ระบบจองร้านกาแฟ</h1>

    <!-- แสดงรายการร้านคาเฟ่ -->
    <CoffeeShopList :coffeeShops="coffeeShops" />

    <!-- แสดงฟอร์มการจอง -->
    <ReservationForm @reserve="reserveCoffeeShop" />
  </div>
</template>

<script>
import CoffeeShopList from './components/CoffeeShopList.vue';
import ReservationForm from './components/ReservationForm.vue';

export default {
  data() {
    return {
      coffeeShops: [
        { id: 1, name: 'ร้าน A', available: true },
        { id: 2, name: 'ร้าน B', available: false },
        // เพิ่มร้านคาเฟ่เพิ่มเติมตามต้องการ
      ],
    };
  },
  components: {
    CoffeeShopList,
    ReservationForm,
  },
  methods: {
    reserveCoffeeShop(reservation) {
      // นี่คือฟังก์ชันที่จะเรียกเมื่อมีการจองร้านคาเฟ่
      // คุณสามารถจัดการข้อมูลการจองที่นี่ เช่น เพิ่มการจองลงในรายการ
      // และอัปเดตสถานะของร้านคาเฟ่
      console.log('การจองร้านกาแฟ:', reservation);
    },
  },
};
</script>
