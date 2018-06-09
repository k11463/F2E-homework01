<template>
    <div>
        <div class="soto">
            <div class="addList">
                <label for="addList" class="addLabel">
                    <i class="fas fa-plus"></i>
                    <div class="addtxt">新增事項</div> 
                </label>
                <input type="checkbox" class="addListInput" id="addList">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
}
</script>

<style>
*{
    user-select: none;
}
.soto{
    height: 900px;
    border: 1px solid;
}
.addList{
    border: 1px solid;
    height: 100px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.addListInput{
    width: 30px;
    background-color: aqua;
}
.addLabel{
    width: 600px;
    height: 60px;
    background-color: #fff;
    border: 1px solid gray;
    border-radius: 5px;
    padding: 5px 0px 0px 15px;
    cursor: text;
}
i{
    font-size: 36px;
    float: left;
    margin-top: 5px;
    color: gray;
}
.addtxt{
    font-size: 30px;
    float: left;
    margin-left: 15px;
    color: gray;
}
input{
    display: none;
}
</style>

