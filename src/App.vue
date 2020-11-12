<template>
  <div class="container">
    <form action="#" method="#" class="form">
      <h3 class="heading">Giải Phương Trình Bậc 2</h3>
      <p class="equation">ax2 + bx + c = 0</p>
      <div class="manager">
        <div class="form-group">
          <label for="" class="form-label">Nhập cơ số a</label><br />
          <input v-model="a" type="text" /><br />
        </div>

        <div class="form-group">
          <label for="" class="form-label">Nhập cơ số b</label><br />
          <input v-model="b" type="text" /><br />
        </div>

        <div class="form-group">
          <label for="" class="form-label">Nhập cơ số c</label><br />
          <input v-model="c" type="text" />
        </div>
      </div>
      <div class="button">
        <button class="form-submit" @click="tinh()">Kết Quả</button>
      </div>
      <span> {{ deltaa }} </span><br />
      <span> {{ mess }}</span
      ><br />
      <span>{{ empty }}</span
      ><br />
      <span> {{ double2 }}</span
      ><br />
      <span> {{ double }}</span>
    </form>
  </div>
</template>
<script>
import("@/assets/css/style.css");

export default {
  name: "App",

  data() {
    return {
      a: "",
      b: "",
      c: "",
      deltaa: "",
      mess: "",
      empty: "",
      double: "",
      double2: "",
    };
  },
  components: {},

  methods: {
    tinh() {
      const delta = this.b * this.b - 4 * this.a * this.c;
       this.deltaa = "  delta la " +delta ;
     
      var x1, x2;
      if (delta === 0) {
        x1 = -this.b / (2 * this.a);
        this.mess = 'nghiem khep x1 = x2 = ' +x1;
      } else if (delta < 0) {
        this.empty = "phuong trinh vo nghiem";
      } else {
        x1 = (-this.b - Math.sqrt(delta)) / (2 * this.a);
        this.double2 = "pt co 2 nghiem phan biet  x1 la :" + x1;
        x2 = (-this.b + Math.sqrt(delta)) / (2 * this.a);
        this.double = "x2 la:" + x2;
      }
      console.log(1)

    },
  },
};
</script>

<style>
</style>
