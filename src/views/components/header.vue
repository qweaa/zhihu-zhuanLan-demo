<style scoped>
.mint-header {
    font-size: 16px;
    height: 45px;
}

.mint-popup {
    width: 60%;
    height: 100%;
    padding: 15px;
}

.userImg img {
    width: 35px;
    height: 35px;
    border-radius: 50%;
}

.bottom-action {
    position: absolute;
    bottom: 35%;
    transform: translateY(-50%);
    width: calc(100% - 30px);
}

.bottom-action.login {
    bottom: 15px;
    transform: none;
}

.bottom-action button {
    width: 100%;
}

.head-portrait {
    position: absolute;
    text-align: center;
    width: calc(100% - 30px);
    top: 40%;
    transform: translateY(-50%);
}

.head-portrait.login {
    top: 15px;
    transform: none;
}

.head-portrait img {
    width: 80px;
    height: 80px;
    border-radius: 50%;
}
</style>

<template>
    <div class="header">
        <mt-header :title="title" :fixed="fixed">
            <span @click="back()" slot="left" v-show="showBack">
                <mt-button icon="back">返回</mt-button>
            </span>
            <div class="userImg" slot="right" @click="popupVisible = !popupVisible">
                <img src="../../images/userDefault.jpg" alt="">
            </div>
        </mt-header>
        <mt-popup v-model="popupVisible" position="right">
            <div class="head-portrait">
                <img src="../../images/userDefault.jpg" alt="">
            </div>
            <div class="bottom-action">
                <mt-button type="primary" size="large" v-show="isLogin">登陆</mt-button>
                <mt-button type="danger" size="small" v-show="!isLogin">退出登陆</mt-button>
            </div>
        </mt-popup>
    </div>
</template>
<script>
import router from "vue-router"
import axios from "axios";

export default {
    data() {
        return {
            popupVisible: false,
            isLogin: true
        }
    },
    methods:{
        back(){
            this.$router.back(-1)
        }
    },
    props: ["title","showBack","fixed"],
    mounted(){
        //登陆的
        // axios.get("http://127.0.0.1:9999?loginName=13729883532&password=0147258369qwe").then((data) => {
        //     console.log(data.data.cookie);
        //     console.log(JSON.parse(data.data.text))
        // }).catch((err) => {
        //     console.log(err)
        // })
    }













    // beforeRouteEnter(to, from, next) {
    //     this.title = to.meta.title;
    // },
    // 路由改变前，组件就已经渲染完了
    // 逻辑稍稍不同
    // watch: {
    //     $route() {
    //         this.title = this.$route.meta.title;
    //     }
    // }
}
</script>
