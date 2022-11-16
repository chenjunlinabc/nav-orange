<template>
    <div class="homenav-main">
        <div class="homeNav-data">
            <div class="homeNav-text">
                添加自定义网站
            </div>
            <div class="homeNav-text" id="homenav-text-note">
                设置将永远存储在您的浏览器里，除非您清理缓存或者主动删除了
            </div>
            <div class="homenav-input">
                <input type="text" ref="urlName" placeholder="网站名称" required="required" />
                <input type="text" ref="urlData" placeholder="网站网址" value="https://" required="required" />
            </div>
            <div class="homenav-botton">
                <button type="submit" id="homenav-add" @click="HomeNavAdd()">添加</button>
                <button type="button" id="homenav-no" @click="HomeNavno()">取消</button>
            </div>
        </div>
    </div>
</template>
<script>
import { defineStore } from 'pinia'
export const useNavStore = defineStore('homeNav', {
    state: () => {
        return {
            homeNavAddyes: false
        }
    },
    actions: {
        AddToNav() {
            this.homeNavAddyes = true
        },
    }
})
export default {
    name: 'HomeNav',
    methods: {
        HomeNavno(){
            const NavStore = useNavStore()
            NavStore.homeNavAddyes = false
        },
        HomeNavAdd(){
            const nameUrl = this.$refs.urlName.value
            const Urldata = this.$refs.urlData.value
            const NavStore = useNavStore()
            NavStore.homeNavAddyes = false
            let UrlDataMain = []
            if (localStorage.getItem('Links')){
                UrlDataMain = JSON.parse(localStorage.getItem('Links'))
            }
            UrlDataMain.push({
                'name': nameUrl,
                'url': Urldata
            })
            localStorage.setItem("Links", JSON.stringify(UrlDataMain))
            
            
        }
    }
}



</script>