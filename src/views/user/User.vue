<template>
  <div class="user">
    <div class="image">
      <img :src="user.avatarUrl" />
    </div>
    <p class="name">{{ user.nickname }}</p>

    <!-- <p class="sign">{{ user.signature }}</p> -->
    <div class="logout" @click="logout">登出</div>
  </div>
</template>

<script>
import Cookies from "js-cookie";
export default {
  name: "User",
  components: {},
  props: {},
  data() {
    return {
      user: null,
    };
  },
  computed: {},
  beforeRouteEnter(to, from, next) {
    next((vm) => {
      if (!vm.$store.state.user) {
        next("/login");
      } else {
        next();
      }
    });
  },
  created() {
    if (Cookies.get("profile")) this.user = JSON.parse(Cookies.get("profile"));
  },
  methods: {
    logout() {
      Cookies.remove("profile");
      Cookies.remove("MUSIC_U");
      Cookies.remove("__csrf");
      Cookies.remove("NMTID");
      document.cookie = "MUSIC_U=1";
      this.$store.commit("userClear");
      this.$router.push("/login");
    },
  },
};
</script>

<style lang='scss' scoped>
.user {
  height: 400rpx !important;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  .image {
    text-align: center;
    margin: 5rem 0 0 0;
    img {
      width: 30vw;
      margin: 1rem;
    }
  }

  .name {
    font-size: 3rem;
    margin: 1rem 0;
  }

  .logout {
    margin: 5rem 0 -5rem 0;
    font-size: 3rem;
  }
}
</style>