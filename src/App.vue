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

      <span v-if="err_msg">{{ err_msg }}</span>

      <!-- <div v-if="danhtinh"> -->
        <div v-if="delta == 0"> {{ x1 }}>

        </div>

        <div v-else-if="delta > 0">
          {{ x1 }},{{ x2 }}
          <span> </span>
        </div>

        <div v-else>
          {{ x1 }}
          <span> </span>
          <button @click="reset()">retset</button>
        </div>

        
      <!-- </div> -->
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
      x1: "",
      x2: "",
      err_msg: "",
    };
  },
  components: {},

  methods: {
    tinh() {
      
      
      if (!Number.isInteger(parseInt(this.a)) || !Number.isInteger(parseInt(this.b)) ||!Number.isInteger(parseInt(this.a))) {
        this.err_msg = " loi k phai so" ;
        return
        
      }

      const delta = this.b * this.b - 4 * this.a * this.c;
      this.deltaa = "delta la " + delta;
       if (delta === 0) {
        this.x1 = "x1 :" + -this.b / (2 * this.a);
      } else if (delta < 0) {
        this.x1 = "vo nghiem";
      } else {
        this.x1 = "x1:" + (-this.b - Math.sqrt(delta)) / (2 * this.a);
        this.x2 = "x2 :" + (-this.b + Math.sqrt(delta)) / (2 * this.a);
      }
    },

    reset() {
      this.danhtinh = false
      this.a =''
      this.b=''
      this.c=''
      this.deltaa=''
      this.err_msg =""
      this.x1=''
      this.x2=''
    },
  },
};
</script>

<style>
</style>
