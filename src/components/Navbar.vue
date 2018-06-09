<template>
    <div class="soto">
        <ul>
            <div class="allLi">
                <router-link class="liNaka" :to="{path: '/'}">
                    <li :class="List01" @click="chgPage(0)">
                        新增事項
                    </li>
                </router-link>
                
                <router-link class="liNaka" :to="{path: '/isIng'}">
                    <li :class="List02" @click="chgPage(1)">
                        進行中
                    </li>
                </router-link>

                <router-link class="liNaka" :to="{path: '/complete'}">
                    <li :class="List03" @click="chgPage(2)">
                    完成事項
                    </li>
                </router-link>
            </div>
        </ul>
    </div>
</template>

<script>
export default {
    data(){
        return {
            liCount: 0
        }
    },
    methods:{
        chgPage(val){
            this.liCount = val;
        }
    },
    computed:{
        List01(){
            if (this.liCount == 0){
                return "checked";
            }
        },
        List02(){
            if (this.liCount == 1){
                return "checked";
            }
        },
        List03(){
            if (this.liCount == 2){
                return "checked";
            }
        }
    }
}
</script>

<style scoped>
*{
    font-family: "標楷體"
}
ul{
    margin: 0px;
    padding: 0px;
    align-items: center;
    justify-content: space-around;
    display: flex;
}
li{
    width: 130px;
    height: 50px;
    float: left;
    align-items: center;
    justify-content: space-around;
    display: flex;
    font-size: 18px;
    cursor: pointer;
    user-select: none;
}
ul li.checked{
    border-bottom: 4px solid #00408B;
    color: white;
}
.liNaka{
    color: #00408B;
    text-decoration: none;
}
.liNaka:hover{
    color: #fff;
}
.allLi{
    height: 50px;
    width: 550px;
    align-items: center;
    justify-content: space-around;
    display: flex;
}
.soto{
    height: 50px;
    background-color: #4A90E2;
}
</style>
