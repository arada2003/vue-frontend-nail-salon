<template>
    <div id="head1">
        <div class="row" style="padding-left: 50px; padding-right: 50px;">
            <div class="col-7" style="padding-top: 30px; padding-left: 50px;">
                <!-- <h6 class="detail">รูปแบบ</h6> -->
                <div class="image-container">
                    <img v-if="file" :src="fileUrl" alt="Uploaded Image" class="uploaded-image">
                </div>
                <div style="padding: 20px;">
                    <input type="file" @change="handleFileUpload">
                </div>
            </div>
            <div class="col-5">
                <div style="padding-right: 200px; padding-top: 20px;">
                    <h4 class="detail">
                        <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" fill="currentColor"
                            class="bi bi-clipboard-check" viewBox="0 0 16 16">
                            <path fill-rule="evenodd"
                                d="M10.854 7.146a.5.5 0 0 1 0 .708l-3 3a.5.5 0 0 1-.708 0l-1.5-1.5a.5.5 0 1 1 .708-.708L7.5 9.793l2.646-2.647a.5.5 0 0 1 .708 0" />
                            <path
                                d="M4 1.5H3a2 2 0 0 0-2 2V14a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V3.5a2 2 0 0 0-2-2h-1v1h1a1 1 0 0 1 1 1V14a1 1 0 0 1-1 1H3a1 1 0 0 1-1-1V3.5a1 1 0 0 1 1-1h1z" />
                            <path
                                d="M9.5 1a.5.5 0 0 1 .5.5v1a.5.5 0 0 1-.5.5h-3a.5.5 0 0 1-.5-.5v-1a.5.5 0 0 1 .5-.5zm-3-1A1.5 1.5 0 0 0 5 1.5v1A1.5 1.5 0 0 0 6.5 4h3A1.5 1.5 0 0 0 11 2.5v-1A1.5 1.5 0 0 0 9.5 0z" />
                        </svg>เพิ่มรูปแบบเล็บเข้าสู่หน้าร้าน
                    </h4>
                    <div style="padding: 20px;">
                        <div class="text-left row mb-3">
                            <div class="col-12">
                                <label class="mb-2 sr-only" for="inline-form-input-name"><svg
                                        xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                        class="bi bi-stars" viewBox="0 0 16 16">
                                        <path
                                            d="M7.657 6.247c.11-.33.576-.33.686 0l.645 1.937a2.89 2.89 0 0 0 1.829 1.828l1.936.645c.33.11.33.576 0 .686l-1.937.645a2.89 2.89 0 0 0-1.828 1.829l-.645 1.936a.361.361 0 0 1-.686 0l-.645-1.937a2.89 2.89 0 0 0-1.828-1.828l-1.937-.645a.361.361 0 0 1 0-.686l1.937-.645a2.89 2.89 0 0 0 1.828-1.828zM3.794 1.148a.217.217 0 0 1 .412 0l.387 1.162c.173.518.579.924 1.097 1.097l1.162.387a.217.217 0 0 1 0 .412l-1.162.387A1.73 1.73 0 0 0 4.593 5.69l-.387 1.162a.217.217 0 0 1-.412 0L3.407 5.69A1.73 1.73 0 0 0 2.31 4.593l-1.162-.387a.217.217 0 0 1 0-.412l1.162-.387A1.73 1.73 0 0 0 3.407 2.31zM10.863.099a.145.145 0 0 1 .274 0l.258.774c.115.346.386.617.732.732l.774.258a.145.145 0 0 1 0 .274l-.774.258a1.16 1.16 0 0 0-.732.732l-.258.774a.145.145 0 0 1-.274 0l-.258-.774a1.16 1.16 0 0 0-.732-.732L9.1 2.137a.145.145 0 0 1 0-.274l.774-.258c.346-.115.617-.386.732-.732z" />
                                    </svg> รหัสรูปแบบ</label>
                                <b-form-input v-model="patternID" id="inline-form-input-name"
                                    class="mb-2 mr-sm-2 mb-sm-0" placeholder=""></b-form-input>
                            </div>
                        </div>
                        <div class="text-left row mb-3">
                            <div class="col-6">
                                <label class="mb-2 sr-only" for="inline-form-input-name">ชื่อรูปแบบ</label>
                                <b-form-input v-model="patternName" id="inline-form-input-name"
                                    class="mb-2 mr-sm-2 mb-sm-0" placeholder=""></b-form-input>
                            </div>
                            <div class="col-6">
                                <label class="mb-2 sr-only" for="inline-form-input-name">ราคาขาย(บาท)</label>
                                <b-form-input id="inline-form-input-name" v-model="patternPrice"
                                    class="mb-2 mr-sm-2 mb-sm-0" placeholder=""></b-form-input>
                            </div>
                        </div>
                        <b-button variant="outline-primary" @click="addProduct"><svg xmlns="http://www.w3.org/2000/svg"
                                width="16" height="16" fill="currentColor" class="bi bi-plus-lg" viewBox="0 0 16 16">
                                <path fill-rule="evenodd"
                                    d="M8 2a.5.5 0 0 1 .5.5v5h5a.5.5 0 0 1 0 1h-5v5a.5.5 0 0 1-1 0v-5h-5a.5.5 0 0 1 0-1h5v-5A.5.5 0 0 1 8 2" />
                            </svg> เพิ่มรูปแบบ</b-button>
                    </div>
                </div>
            </div>
        </div>
        <div style="padding-left: 200px; padding-right: 200px; padding-top: 40px;">
            <input class="search" type="text" v-model="searchByID" placeholder="ค้นหาด้วยรหัสรูปแบบ">
            <div style="padding-top: 20px;">
                <table class="table table-hover table-bordered " id="example">
                    <thead>
                        <tr>
                            <th colspan="4" class="table-info">
                                ข้อมูลรูปแบบเล็บในร้านค้า
                            </th>
                        </tr>
                    </thead>
                    <thead class="table-info">
                        <tr>
                            <th>รหัสรูปแบบ</th>
                            <th>ชื่อรูปแบบ</th>
                            <th>ราคาขาย(บาท)</th>
                            <th></th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr v-for="product in filteredProducts" :key="product.pattern_id">
                            <td>{{ product.pattern_id }}</td>
                            <td>{{ product.pattern_Name }}</td>
                            <td>{{ product.pattern_Price }}</td>
                            <td>
                                <b-button class="btn btn-light btn-outline-warning" @click="editProduct(product)"> <svg
                                        xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                                        class="bi bi-pencil-square" viewBox="0 0 16 16">
                                        <path
                                            d="M15.502 1.94a.5.5 0 0 1 0 .706L14.459 3.69l-2-2L13.502.646a.5.5 0 0 1 .707 0l1.293 1.293zm-1.75 2.456-2-2L4.939 9.21a.5.5 0 0 0-.121.196l-.805 2.414a.25.25 0 0 0 .316.316l2.414-.805a.5.5 0 0 0 .196-.12l6.813-6.814z" />
                                        <path fill-rule="evenodd"
                                            d="M1 13.5A1.5 1.5 0 0 0 2.5 15h11a1.5 1.5 0 0 0 1.5-1.5v-6a.5.5 0 0 0-1 0v6a.5.5 0 0 1-.5.5h-11a.5.5 0 0 1-.5-.5v-11a.5.5 0 0 1 .5-.5H9a.5.5 0 0 0 0-1H2.5A1.5 1.5 0 0 0 1 2.5z" />
                                    </svg> แก้ไข</b-button> <b-button class="btn btn-light btn-outline-danger"
                                    @click="deleteProduct(product.pattern_id)"> <svg xmlns="http://www.w3.org/2000/svg"
                                        width="16" height="16" fill="currentColor" class="bi bi-trash3-fill"
                                        viewBox="0 0 16 16">
                                        <path
                                            d="M11 1.5v1h3.5a.5.5 0 0 1 0 1h-.538l-.853 10.66A2 2 0 0 1 11.115 16h-6.23a2 2 0 0 1-1.994-1.84L2.038 3.5H1.5a.5.5 0 0 1 0-1H5v-1A1.5 1.5 0 0 1 6.5 0h3A1.5 1.5 0 0 1 11 1.5m-5 0v1h4v-1a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0-.5.5M4.5 5.029l.5 8.5a.5.5 0 1 0 .998-.06l-.5-8.5a.5.5 0 1 0-.998.06m6.53-.528a.5.5 0 0 0-.528.47l-.5 8.5a.5.5 0 0 0 .998.058l.5-8.5a.5.5 0 0 0-.47-.528M8 4.5a.5.5 0 0 0-.5.5v8.5a.5.5 0 0 0 1 0V5a.5.5 0 0 0-.5-.5" />
                                    </svg> ลบ</b-button>
                            </td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <b-modal id="head1" ref="myModalRef" title="แก้ไขข้อมูล" hide-footer>
                <div style="padding: 20px;">
                    <div class="text-left row mb-3">
                        <div class="col-md-4">
                            <label class="mb-2 sr-only" for="inline-form-input-name">รหัสรูปแบบ</label>
                            <b-form-input v-model="patternIDEdit" id="inline-form-input-name"
                                class="mb-2 mr-sm-2 mb-sm-0" placeholder="Pattern ID"></b-form-input>
                        </div>
                        <div class="col-md-4">
                            <label class="mb-2 sr-only" for="inline-form-input-name">ชื่อรูปแบบ</label>
                            <b-form-input v-model="patternNameEdit" id="inline-form-input-name"
                                class="mb-2 mr-sm-2 mb-sm-0" placeholder="Pattern Name"></b-form-input>
                        </div>
                        <div class="col-md-4">
                            <label class="mb-2 sr-only" for="inline-form-input-name">ราคาขาย</label>
                            <b-form-input id="inline-form-input-name" v-model="patternPriceEdit"
                                class="mb-2 mr-sm-2 mb-sm-0" placeholder="Pattern Price"></b-form-input>
                        </div>
                    </div>
                    <b-button class="btn btn-light btn-outline-success" @click="updateProduct">อัปเดต</b-button>
                </div>
            </b-modal>
        </div>
    </div>
</template>

<script>
// import axios from 'axios';

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
            searchQuery: "",
            searchByID: "",
            file: null,
            fileUrl: null
        }
    },
    computed: {
        filteredProducts() {
            return this.products.filter(product => {
                return product.pattern_id.toLowerCase().includes(this.searchQuery.toLowerCase()) &&
                    product.pattern_id.toLowerCase().includes(this.searchByID.toLowerCase());
            });
        }
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
                    this.file = null;
                    this.fileUrl = null;
                    const input = document.querySelector('input[type="file"]');
                    input.value = '';
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
            const confirmed = window.confirm("คุณต้องการลบข้อมูลหรือไม่?");
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
        handleFileUpload(event) {
            this.file = event.target.files[0];
            this.fileUrl = URL.createObjectURL(this.file);
        },
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');
@import '~bootstrap/dist/css/bootstrap.min.css';

#head1 {
    font-family: "Itim", cursive;
    font-weight: 400;
    font-style: normal;
}

.image-container {
    width: 70%;
    height: 300px;
    overflow: hidden;
    border: 1px solid rgb(138, 138, 138);
    margin-left: 100px;
}

.uploaded-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.upload-btn {
    margin-top: 10px;
    width: 150px;
    border-radius: 8px;
    background-color: #007bff;
    color: #fff;
    border: none;
    transition: background-color 0.3s ease;
}

.detail {
    /* border: 1px solid rgb(138, 138, 138); */
    width: 100%;
    height: 30px;
    border-radius: 8px;
    text-align: center;
    margin-top: 30px;
    /* background-color:S rgb(230, 230, 230); */
}

.search {
    border-radius: 8px;
    height: 20px;
    padding: 20px;
    width: 23%;
}
</style>