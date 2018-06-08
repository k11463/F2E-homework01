<template>
    <div class="container">
        <div class="soto">
            <ul>
                <div class="allLi">
                    <li>
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
    </div>
</template>

<script>
export default {

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
    font-size: 20px;
    cursor: pointer;
    user-select: none;
}
li:hover{
    background-color: #009fcc;
}
li:active{
    border-bottom: 3px solid black;
}
.liNaka{
    color: black;
    text-decoration: none;
}
.liNaka:hover{
    color: white;
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
    background-color: #0bf;
}
</style>
