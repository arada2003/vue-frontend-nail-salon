<!-- <template>
  <div id="head1" style="padding-top: 10px; padding-left: 50px; padding-right: 50px;">
    <b-modal ref="myModalRef" title="แก้ไขข้อมูล" hide-footer>
      <div style="padding: 20px;">
        <div class="text-left row mb-3">
          <div class="col-md-4">
            <label class="mb-2 sr-only" for="inline-form-input-name">รหัสรูปแบบ</label>
            <b-form-input v-model="patternIDEdit" id="inline-form-input-name" class="mb-2 mr-sm-2 mb-sm-0"
              placeholder="Pattern ID"></b-form-input>
          </div>
          <div class="col-md-4">
            <label class="mb-2 sr-only" for="inline-form-input-name">ชื่อรูปแบบ</label>
            <b-form-input v-model="patternNameEdit" id="inline-form-input-name" class="mb-2 mr-sm-2 mb-sm-0"
              placeholder="Pattern Name"></b-form-input>
          </div>
          <div class="col-md-4">
            <label class="mb-2 sr-only" for="inline-form-input-name">ราคาขาย</label>
            <b-form-input id="inline-form-input-name" v-model="patternPriceEdit" class="mb-2 mr-sm-2 mb-sm-0"
              placeholder="Pattern Price"></b-form-input>
          </div>
        </div>
        <b-button class="btn btn-light btn-outline-success" @click="updateProduct">อัปเดต</b-button>
      </div>
    </b-modal>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [],
      patternID: "",
      patternName: "",
      patternPrice: "",
      //Edit
      patternIDEdit: "",
      patternNameEdit: "",
      patternPriceEdit: "",
    };
  },
  mounted() {
    this.getProduct();
  },

  methods: {
    getAPI() {
      this.axios.get("http://localhost:8001/get_all_product/").then((res) => {
        console.log(res);
      });
    },
    // เปิด Modal
    showModal() {
      this.$refs.myModalRef.show();
    },
    // ปิด Modal
    hideModal() {
      this.$refs.myModalRef.hide();
    },

    async getProduct() {
      try {
        const response = await this.$http(
          "http://localhost:8001/get_all_product/"
        );
        if (response.status == 200) {
          console.log(response.data);
          this.products = response.data;
        } else {
          throw { response };
        }
      } catch (error) {
        console.log(error);
      }
    },
    async addProduct() {
      if (!this.patternID || !this.patternName || !this.patternPrice) {
        alert('กรุณากรอกข้อมูลให้ครบทุกช่อง');
        return;
      }
      let bodyJson = {
        pattern_id: this.patternID,
        pattern_Name: this.patternName,
        pattern_Price: this.patternPrice,
      };
      try {
        const response = await this.axios.post(
          "http://localhost:8001/create_product/",
          bodyJson
        );
        if (response.status === 201) {
          console.log(response);
          this.getProduct();
          alert("เพิ่มข้อมูลสำเร็จ");
          this.patternID = "";
          this.patternName = "";
          this.patternPrice = "";
          this.getProduct;
        } else {
          throw { response };
        }
      } catch (error) {
        console.log(error);
      }
    },
    async editProduct(product) {
      console.log(product);
      this.patternIDEdit = product.pattern_id;
      this.patternNameEdit = product.pattern_Name;
      this.patternPriceEdit = product.pattern_Price;
      this.showModal();
    },
    async updateProduct() {
      let bodyJson = {
        pattern_Name: this.patternNameEdit,
        pattern_Price: this.patternPriceEdit,
      };
      try {
        const response = await this.axios.put(
          `http://localhost:8001/update_product/${this.patternIDEdit}`,
          bodyJson
        );
        if (response.status === 200) {
          console.log(response);
          alert("อัปเดตข้อมูลสำเร็จ");
          this.hideModal();
          this.getProduct();
        } else {
          throw { response };
        }
      } catch (error) {
        console.log(error);
      }
    },
    async deleteProduct(id) {
      const confirmed = window.confirm("คุณต้องการลบสินค้านี้หรือไม่?");
      if (confirmed) {
        try {
          const response = await this.axios.delete(
            `http://localhost:8001/delete_product/${id}`
          );
          if (response.status === 200) {
            alert("ลบข้อมูลสำเร็จ");
            this.getProduct();
          } else {
            throw { response };
          }
        } catch (error) {
          console.error("Error deleting product:", error);
        }
      }
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');

#div {
  color: rgb(35, 70, 230);
}

.space {
  width: auto;
  margin-left: 475px;
  margin-right: 500px;
  color: rgb(35, 70, 230);
}

#head1 {
  font-family: "Itim", cursive;
  font-weight: 400;
  font-style: normal;
  color: rgb(35, 70, 230);
}
</style> -->

