<template>
    <HomeNav v-if="HomeNavStore.homeNavAddyes"/>
    <div class="search-view">
        <div class="other">
            <div class="box">
                <h3 class="homeNav">我的导航</h3>
                <div class="revise" @click="rmNav()">清除</div>
            </div>
            
            <ul>
                <li v-for="navTO in UrlData" class="Homenav">
                    <a v-bind:href="navTO.url"  rel="noopener noreferrer" target="_blank">{{ navTO.name }}</a>
                </li>
                <li>
                    <span class="AddTo" @click="AddNav()">+</span>
                </li>
                
            </ul>
        </div>
        <div class="tech">
            <div class="box">
                <h3 class="search-h">技术</h3>
            </div>
            <ul>
                <li>
                    <a href="https://developer.mozilla.org/zh-CN/" rel="noopener noreferrer" target="_blank">MDN</a>
                </li>
                <li>
                    <a href="https://codeforces.com/" rel="noopener noreferrer" target="_blank">Codeforces</a>
                </li>
                <li>
                    <a href="https://leetcode-cn.com/" rel="noopener noreferrer" target="_blank">力扣</a>
                </li>
                <li>
                    <a href="https://www.nowcoder.com/" rel="noopener noreferrer" target="_blank">牛客</a>
                </li>
                <li>
                    <a href="https://github.com" rel="noopener noreferrer" target="_blank">Github</a>
                </li>
                <li>
                    <a href="http://gitee.com" rel="noopener noreferrer" target="_blank">Gitee</a>
                </li>
                <li>
                    <a href="https://stackoverflow.com/" rel="noopener noreferrer" target="_blank">StackOverflow</a>
                </li>
                <li>
                    <a href="https://cn.v2ex.com" rel="noopener noreferrer" target="_blank">V2EX</a>
                </li>
                <li>
                    <a href="https://segmentfault.com/" rel="noopener noreferrer" target="_blank">思否</a>
                </li>
                <li>
                    <a href="https://juejin.cn/" rel="noopener noreferrer" target="_blank">稀土掘金</a>
                </li>
                <li>
                    <a href="https://www.zhihu.com/" rel="noopener noreferrer" target="_blank">知乎</a>
                </li>
                <li>
                    <a href="https://www.csdn.net/" rel="noopener noreferrer" target="_blank">CSDN</a>
                </li>
                <li>
                    <a href="https://www.cnblogs.com/" rel="noopener noreferrer" target="_blank">博客园</a>
                </li>
                <li>
                    <a href="https://superuser.com/" rel="noopener noreferrer" target="_blank">superuser</a>
                </li>
            </ul>
        </div>
        
        <div class="film">
            <div class="box">
                <h3 class="search-h">影视</h3>
            </div>
            <ul>
                <li>
                    <a href="https://v.qq.com/" rel="noopener noreferrer" target="_blank">腾讯视频</a>
                </li>
                <li>
                    <a href="https://www.iqiyi.com/" rel="noopener noreferrer" target="_blank">爱奇艺</a>
                </li>
                <li>
                    <a href="https://youku.com/" rel="noopener noreferrer" target="_blank">优酷</a>
                </li>
                <li>
                    <a href="https://bilibili.com/" rel="noopener noreferrer" target="_blank">哔哩哔哩</a>
                </li>
                <li>
                    <a href="https://www.douyu.com/" rel="noopener noreferrer" target="_blank">斗鱼直播</a>
                </li>
                <li>
                    <a href="https://www.huya.com/" rel="noopener noreferrer" target="_blank">虎牙直播</a>
                </li>

            </ul>
        </div>
        <div class="tools">
            <div class="box">
                <h3 class="search-h">工具</h3>
            </div>
            <ul>
                <li>
                    <a href="https://www.bejson.com/" rel="noopener noreferrer" target="_blank">BEJSON</a>
                </li>
                <li>
                    <a href="https://fanyi.baidu.com/" rel="noopener noreferrer" target="_blank">百度翻译</a>
                </li>
                <li>
                    <a href="https://mail.qq.com/" rel="noopener noreferrer" target="_blank">QQ邮箱</a>
                </li>
                <li>
                    <a href="https://mail.126.com/" rel="noopener noreferrer" target="_blank">网易邮箱</a>
                </li>
                <li>
                    <a href="https://www.iconfont.cn/" rel="noopener noreferrer" target="_blank">iconfont</a>
                </li>
                <li>
                    <a href="https://pan.baidu.com/" rel="noopener noreferrer" target="_blank">百度网盘</a>
                </li>
                <li>
                    <a href="https://www.aliyundrive.com/" rel="noopener noreferrer" target="_blank">阿里网盘</a>
                </li>
                <li>
                    <a href="https://mirrors.tuna.tsinghua.edu.cn/" rel="noopener noreferrer" target="_blank">清华大学开源软件镜像站</a>
                </li>
                <li>
                    <a href="https://cloud.tencent.com/" rel="noopener noreferrer" target="_blank">腾讯云</a>
                </li>
                <li>
                    <a href="https://www.aliyun.com/" rel="noopener noreferrer" target="_blank">阿里云</a>
                </li>
                <li>
                    <a href="https://jujuso.com/" rel="noopener noreferrer" target="_blank">优聚搜</a>
                </li>
                <li>
                    <a href="https://www.netlify.com/" rel="noopener noreferrer" target="_blank">Netlify</a>
                </li>
                <li>
                    <a href="https://vercel.com/" rel="noopener noreferrer" target="_blank">Vercel</a>
                </li>
                <li>
                    <a href="https://cupfox.app/" rel="noopener noreferrer" target="_blank">茶杯狐</a>
                </li>
            </ul>
        </div>
        <div class="info">
            <div class="box">
                <h3 class="search-h">资讯</h3>
            </div>
            <ul>
                <li>
                    <a href="https://www.ithome.com/" rel="noopener noreferrer" target="_blank">IT之家</a>
                </li>
                <li>
                    <a href="https://weibo.com/" rel="noopener noreferrer" target="_blank">新浪微博</a>
                </li>
                <li>
                    <a href="https://www.oschina.net/" rel="noopener noreferrer" target="_blank">OSCHINA</a>
                </li>
            </ul>
        </div>
        <div class="other">
            <div class="box">
                <h3 class="search-h">其他</h3>
            </div>
            <ul>
                <li>
                    <a href="https://www.taobao.com/" rel="noopener noreferrer" target="_blank">淘宝</a>
                </li>
                <li>
                    <a href="https://www.jd.com/" rel="noopener noreferrer" target="_blank">京东</a>
                </li>
                <li>
                    <a href="https://www.12306.cn/" rel="noopener noreferrer" target="_blank">12306</a>
                </li>
                <li>
                    <a href="https://tieba.baidu.com/" rel="noopener noreferrer" target="_blank">百度贴吧</a>
                </li>
                <li>
                    <a href="https://cjlio.com/" rel="noopener noreferrer" target="_blank">小陈的辣鸡屋</a>
                </li>
            </ul>
        </div>
    </div>
</template>
<script scope>
import HomeNav from "./HomeNav.vue"
import { useNavStore } from "./HomeNav.vue"

export default {
    name: 'SearchView',
    data(){
        const HomeNav = useNavStore()
        return{
            UrlData: JSON.parse(localStorage.getItem('Links')),
            HomeNavStore: HomeNav
        }
    },
    methods: {
        rmNav() {
            if (localStorage.getItem('Links')){
                localStorage.removeItem("Links")
                this.$data.UrlData = JSON.parse(localStorage.getItem('Links'))
            }
        },
        AddNav(){
            const NavStore = useNavStore()
            NavStore.AddToNav()
        }
    },
    components: {
        HomeNav
    },
    beforeUpdate() {
        this.$data.UrlData = JSON.parse(localStorage.getItem('Links'))
    },
}
</script>


