<template>
    <div>
        <div class="soto">
            <div class="addList">
                <label for="addList" class="addLabel">
                    <i class="fas fa-plus"></i>
                    <div class="addtxt">新增事項</div> 
                </label>
                <input type="checkbox" class="addListInput" id="addList">
                <div class="content">
                    <div class="title">
                        <label for="title" class="titleLabel">
                            <div class="titleTxt">
                                新增標題
                            </div>
                            <input type="checkbox" id="title" class="titleInput">
                            <div class="checkmark"></div>
                        </label>
                        <i class="fas fa-pencil-alt pen"></i>
                        <i class="far fa-star star"></i>
                    </div>
                    <div class="time">
                        <div class="timeTitle">
                            <i class="far fa-calendar-alt calendar"></i>
                            <div class="timeTitleTxt">結束時間</div>
                        </div>
                        <div class="timeInput">
                            <input type="date" class="date">
                            <input type="time" id="time">
                        </div>
                    </div>
                    <div class="time">
                        <div class="timeTitle">
                            <i class="far fa-file calendar"></i>
                            <div class="timeTitleTxt">上傳檔案</div>
                        </div>
                        <div class="timeInput">
                            <label for="update" class="updateFile">
                                <div class="updateIcon">
                                    <i class="fas fa-plus"></i>
                                </div>
                                <input type="file" id="update">
                            </label>
                        </div>
                        <div class="comment">
                            <div class="timeTitle">
                                <i class="far fa-comment-dots calendar"></i>
                                <div class="timeTitleTxt">事項內容</div>
                            </div>
                            <div class="commentContent">
                                <textarea cols="80" rows="5" placeholder="請輸入您的內容"></textarea>
                            </div>
                        </div>
                        <div class="btns">
                            <button class="leftbtn btn">
                                <label for="leftbtn" class="btnTxtLeft">
                                    離開
                                    <i class="fas fa-times btnIconLeft" id="leftbtn"></i>
                                </label>
                            </button>
                            <button class="rightbtn btn">
                                <label for="rightbtn" class="btnTxtRight">
                                    增加事項
                                    <i class="fas fa-plus btnIconRight" id="rightbtn"></i>
                                </label>
                            </button>
                        </div>
                    </div>
                </div>
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
input.addListInput{
    display: none;
}
.content{
    width: 600px;
    height: 500px;
    top: 150px;
    border: 1px solid gray;
    position: absolute;
    box-shadow: 8px 8px 8px 0px rgba(0, 0, 0, 0.5);
}
.title{
    border-bottom: 2px solid gray;
    width: 600px;
    height: 70px;
    padding: 12px 0 0 20px;
}
.titleInput{
    width: 24px;
    height: 24px;
    margin-top: 8px;
    color: #fff;
    background-color: #fff;
    float: left;
}
.titleLabel{
    font-size: 24px;
    margin-left: 20px;
    float: left;
    position: relative;
    cursor: pointer;
    user-select: none;
}
.titleLabel input{
    position: absolute;
    opacity: 0;
}
.titleLabel:hover input ~ .checkmark{
    background-color: #aaa;
}
.titleLabel input:checked ~ .checkmark{
    background-color: #2196F3;
}
.titleLabel input:checked ~ .checkmark:after{
    display: block;
}
.titleLabel .checkmark:after{
    left: 7px;
    top: 1px;
    width: 8px;
    height: 16px;
    border: solid white;
    border-width: 0 3px 3px 0;
    transform: rotate(45deg);
}
.checkmark:after{
    content:"";
    position: absolute;
    display: none;
}
.titleTxt{
    margin-left: 50px;
}
.checkmark{
    position: absolute;
    width: 22px;
    height: 22px;
    background-color: #fff;
    top: 10px;
    left: 0;
}
.star{
    color: black;
    font-size: 22px;
    padding: 3px;
    float: right;
    margin-right: 20px;
}
.pen{
    font-size: 24px;
    padding: 3px;
    float: right;
    margin-right: 25px;
    color: #4a90e2;
}
.time{
    height: 70px;
    margin-top: 15px;
}
.timeTitle{
    height: 30px;
    margin-left: 40px;
}
.timeInput{
    height: 40px;
    margin-left: 40px;
}
.calendar{
    font-size: 20px;
    color: black;
    margin-left: 8px;
    float: left;
}
.timeTitleTxt{
    font-size: 19px;
    font-weight: bold;
    margin-left: 9px;
    float: left;
}
.date{
    width: 170px;
    height: 35px;
    padding: 0 0 0 15px;
    color: gray;
    margin-left: 30px;
}
#time{
    width: 170px;
    height: 35px;
    padding: 0 0 0 15px;
    color: gray;
    margin-left: 10px;
}
.updateFile input{
    position: absolute;
    opacity: 0;
}
.updateIcon{
    width: 30px;
    height: 30px;
    background-color: #aaa;
    margin-top: 5px;
    margin-left: 30px;
    cursor: pointer;
}
.updateIcon i{
    font-size: 25px;
    margin-top: 2px;
    margin-left: 4px;
}
.comment{
    height: 180px;
}
.commentContent{
    height: 145px;
    margin-top: 5px;
    display: flex;
    justify-content: center;
}
.commentContent textarea{
    resize: none;
    width: 80%;
    height: 90%;
    padding: 5px 0 0 10px;
}
.btns{
    height: 60px;
    margin-top: 3%;
}
.btns label{
    cursor: pointer;
}
.btn{
    width: 50%;
    height: 100%;
    border-radius: 0px;
}
.leftbtn{
    background-color: #fff;
}
.rightbtn{
    background-color: #4a90e2;
}
.btnIconLeft{
    font-size: 28px;
    color: red;
    margin-right: 15px;
}
.btnTxtLeft{
    font-size: 20px;
    color: red;
    font-weight: bold;
}
.btnIconRight{
    font-size: 28px;
    color: #fff;
    margin-right: 15px;
}
.btnTxtRight{
    font-size: 20px;
    color: #fff;
    font-weight: bold;
}
</style>

