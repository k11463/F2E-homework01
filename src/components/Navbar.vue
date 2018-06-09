<template>
    <div class="soto">
        <ul>
            <div class="allLi">
                <li class="checked">
                   <router-link class="liNaka" :to="{path: '/'}">新增事項</router-link>
                </li>
                <li>
                   <router-link class="liNaka" :to="{path: '/isIng'}">進行中</router-link>
                </li>
                <li>
                   <router-link class="liNaka" :to="{path: '/complete'}">完成事項</router-link>
                </li>
            </div>
        </ul>
    </div>
</template>

<script>
export default {

    mounted(){
        
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
