<template>
    <div>
        <div class="container soto">
            <div class="row addList">

                <div class="col-sm-12 topRow">
                    <label for="addList" class="addLabel">
                        <i class="fas fa-plus titlePlus"></i>
                        <div class="addtxt">新增事項</div> 
                    </label>
                    <input type="checkbox" class="addListInput" id="addList">
                </div>
                
                <div class="col-sm-12 midRow" v-for="(data, id) in datas" :key="data.id">
                    <div class="content">
                        <div class="title">
                            <label for="title" class="titleLabel">
                                <div class="titleTxt">
                                    {{data.title}}
                                </div>
                                <input type="checkbox" id="title" class="titleInput">
                                <div class="checkmark"></div>
                            </label>
                            <i class="fas fa-pencil-alt pen" @click="pen(id)"></i>
                            <i class="far fa-star star"></i>
                        </div>
                        <div class="contentToggle" v-if="data.show">
                            <div class="time">
                                <div class="timeTitle">
                                    <i class="far fa-calendar-alt calendar"></i>
                                    <div class="timeTitleTxt">結束時間</div>
                                </div>
                                <div class="timeInput">
                                    <input type="date" class="date" :value="data.date">
                                    <input type="time" id="time" :value="data.time">
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
                                        <textarea cols="80" rows="5" placeholder="請輸入您的內容">{{ data.comment }}</textarea>
                                    </div>
                                </div>
                                <div class="btns">
                                    <button class="leftbtn btn">
                                        <label for="leftbtn" class="btnTxtLeft">
                                            <i class="fas fa-times btnIconLeft" id="leftbtn">
                                                離開
                                            </i>
                                        </label>
                                    </button>
                                    <button class="rightbtn btn">
                                        <label for="rightbtn" class="btnTxtRight">
                                            <i class="fas fa-plus btnIconRight" id="rightbtn">
                                                增加事項
                                            </i>
                                        </label>
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        var datas = [
            {
                "title": "上班",
                "date": "1986-07-23",
                "time": "07:30:00",
                "update": "",
                "comment": "幹 又要上班了 機掰人",
                "show": false,
            },
            {
                "title": "下班",
                "date": "1986-07-23",
                "time": "17:00:00",
                "update": "",
                "comment": "下班惹~~ 爽~~~~",
                "show": false,
            }
        ]
        return {
            datas: datas,
            show: false,
        }
    },
    methods: {
        pen(id){
            this.datas[id].show = !this.datas[id].show;
        }
    }
}
</script>

<style>
*{
    user-select: none;
}
.topRow{
    height: 50px;
    display: flex;
    justify-content: center;
    margin-top: 20px;
    margin-bottom: 20px;
}
.midRow{
    height: 70px;
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
}
.addList{
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
    height: 50px;
    background-color: #fff;
    border: 1px solid gray;
    border-radius: 5px;
    padding: 0px 0px 0px 15px;
    cursor: pointer;
}
.addLabel:hover{
    background-color: #f2f2f2;
}
.titlePlus{
    font-size: 36px;
    float: left;
    margin-top: 7px;
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
    position: absolute;
}
.title{
    width: 600px;
    height: 70px;
    padding: 12px 0 0 20px;
    border: 1px solid gray;
}
.contentToggle{
    height: 430px;
    border: 1px solid gray;
    box-shadow: 8px 8px 8px 0px rgba(0, 0, 0, 0.5);
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
    background-color: #f2f2f2;
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
    cursor: pointer;
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
    margin-top: 5px;
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
.leftbtn:hover{
    background-color: #f2f2f2;
}
.rightbtn{
    background-color: #4a90e2;
}
.rightbtn:hover{
    background-color: #4587d3
}
.btnIconLeft{
    font-size: 22px;
    color: red;
    margin-right: 15px;
    margin-top: 8px;
}
.btnIconRight{
    font-size: 22px;
    color: #fff;
    margin-right: 15px;
    margin-top: 8px;
}
</style>

