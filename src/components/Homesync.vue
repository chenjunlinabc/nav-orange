<template>
    <div class="homenav-main">
        <div class="homeNav-data">
            <div class="homeNav-text">
                导入数据 / 导出数据
            </div>
            <div class="homeNav-text" id="homenav-text-note">
                设置可以被导入或者导出，这样就不怕数据没了，如果需要导出请点击导出按钮，需要导入则点击导入按钮，上传设置文件请将导出的文件进行上传
            </div>
            <div class="homenav-botton">
                <input type="file" hidden ref="homesyn" accept="application/json">
                <button type="button" id="homenav-add"  @click="HomesyncAdd()">导入</button>
                <button type="button" id="homenav-no" @click="HomesyncGet()" ref="Syncget">导出</button>
                <button type="button" id="kill" @click="HomesyncKill()">取消</button>
            </div>
        </div>
    </div>
    
</template>

<script>
    import { defineStore } from 'pinia'
    export const SyncStore = defineStore('Sync', {
        state: () => {
            return {
                Syncyes: false
            }
        },
        actions: {
            SyncTo() {
                this.Syncyes = true
            },
        }
    })
    export default{
        name: 'Homesync',
        methods: {
            HomesyncKill(){
                const syncStoreyes = SyncStore()
                syncStoreyes.Syncyes = false
            },
            HomesyncAdd(){
                this.$refs.homesyn.dispatchEvent(new MouseEvent('click'))
                this.$refs.homesyn.onchange = (event) => {
                    const file = event.target.files[0]
                    const file_reader = new FileReader()
                    file_reader.onload = () => {
                        const SyncData = JSON.parse(file_reader.result)
                        for (let synci = 0; synci < SyncData.data.length; synci++){
                            let syncDataurl = []
                            if (localStorage.getItem('Links')) {
                                syncDataurl = JSON.parse(localStorage.getItem('Links'))
                            }
                            syncDataurl.push(SyncData.data[synci])
                            localStorage.setItem("Links", JSON.stringify(syncDataurl))
                        }
                    }
                    file_reader.readAsText(file, 'UTF-8')
                }
            },
            HomesyncGet(){
                const SyncGetData = {
                    "data": JSON.parse(localStorage.getItem('Links'))
                }
                const SyncgetJson = "data:text/json;charset=utf-8," + encodeURIComponent(JSON.stringify(SyncGetData))
                const Syncgetdownload = document.createElement('a')
                Syncgetdownload.setAttribute("href", SyncgetJson)
                Syncgetdownload.setAttribute("download", "s-cjlio-com.json")
                Syncgetdownload.click()
                Syncgetdownload.remove()
            }
        }
    }
</script>