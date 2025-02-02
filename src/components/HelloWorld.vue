<template>
  <div id="head1">
    <div class="logonav">
      <span class="navbar-brand" style="width:40px;">
        <img src="@/assets/nail.png">
      </span>
      <div class="nav">
        <a href="#" :class="{ 'active': activeTab === 'customer' }" @click="setActiveTab('customer')">ข้อมูลลูกค้า</a>
        <a href="#" :class="{ 'active': activeTab === 'reservation' }"
          @click="setActiveTab('reservation')">คำสั่งจอง</a>
        <a href="#" :class="{ 'active': activeTab === 'queue' }" @click="setActiveTab('queue')">คิวของลูกค้า</a>
        <a href="#" :class="{ 'active': activeTab === 'nail_design' }" @click="setActiveTab('nail_design')">
          <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" fill="currentColor" class="bi bi-box-seam-fill"
            viewBox="0 0 16 16">
            <path fill-rule="evenodd"
              d="M15.528 2.973a.75.75 0 0 1 .472.696v8.662a.75.75 0 0 1-.472.696l-7.25 2.9a.75.75 0 0 1-.557 0l-7.25-2.9A.75.75 0 0 1 0 12.331V3.669a.75.75 0 0 1 .471-.696L7.443.184l.01-.003.268-.108a.75.75 0 0 1 .558 0l.269.108.01.003zM10.404 2 4.25 4.461 1.846 3.5 1 3.839v.4l6.5 2.6v7.922l.5.2.5-.2V6.84l6.5-2.6v-.4l-.846-.339L8 5.961 5.596 5l6.154-2.461z" />
          </svg>
          คลังรูปแบบเล็บ</a>
        <a href="#" :class="{ 'active': activeTab === 'nail_supply' }"
          @click="setActiveTab('nail_supply')">คลังอะไหล่เล็บ</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 'nail_design'
    }
  },
  methods: {
    setActiveTab(tab) {
      this.activeTab = tab;
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Itim&display=swap');

h3 {
  text-align: center;
  padding-left: 25px;
}

#head1 {
  font-family: "Itim", cursive;
  font-weight: 400;
  font-style: normal;
  font-size: large;
}

.logonav {
  /* border:2px solid red; */
  display: flex;
  justify-content: center;
  height: 65px;
  background-color: aliceblue;
  border-bottom: 2px solid #ddeffc;;
}

.logonav img {
  width: 250px;
  height: 135px;
  padding-bottom: 55px;
  padding-left: 50px;
}

.nav {
  display: flex;
  justify-content: center;
  padding: 10px 60px;
  width: 1200px;
  border-radius: 10px;
  margin: 5px 0 0 50px;
  /*top left bottom right*/
}

.nav a {
  /* border:2px solid red; */
  text-decoration: none;
  margin: 10px 0px 0px 15px;
  font-size: larger;
  letter-spacing: 2px;
  position: relative;
  color: rgb(35, 70, 230);
}

.nav a::after {
  content: '';
  position: absolute;
  width: 10px;
  opacity: 0;
  height: 5px;
  background-image: linear-gradient(to right, #e4af32, #ed4161);
  bottom: -5px;
  left: 50%;
  transform: translateX(-50%);
  border-radius: 25px;
  transition: 0.4s;
}

.nav a:hover::after {
  width: 50%;
  opacity: 1;
}

.logonav .nav a.active {
  /* border:2px solid red; */
  background-color: #ddeffc;
  border-radius: 10px;
  border-bottom-left-radius: 3px;
  border-bottom-right-radius: 3px;
  color: rgb(35, 70, 230);
  padding-bottom: 8px;
  width: 17%;
}
</style>