<template>
    <div>
        <div class="left-box">
            <div class="left-content">
                <p class="param-set">参数设置</p>
                <p>首次预期次数：<input type="number" placeholder="请设置次数"></p>
                 <p>首次预期次数：<input type="number" placeholder="请设置次数"></p>
                  <p>首次预期次数：<input type="number" placeholder="请设置次数"></p>
                   <p>首次预期次数：<input type="number" placeholder="请设置次数"></p>
            </div>
        </div>
    <div class="wraper">
        <lottery
            @lotteryClick="lotteryClick"
            @lotteryDone="lotteryDone"
            :lottery-start="lotteryStart"
            :lottery-prizenum="prizeNum"
            :lottery-prizeno="prizeNo"
            lottery-bg="./static/turnplate-bg.png"
            content-bg="./static/turntable.png"
            pointer-bg="./static/pointer.png"
            :lottery-width="['85%','35%']"
        />
        <p class="tips">Tips:本次抽奖中奖概率为10%,本次抽奖中奖概率为10%,本次抽奖中奖概率为10%</p>
        <p class="tips">Tips:本次抽奖中奖概率为10%,本次抽奖中奖概率为10%</p>
        <p class="tips">Tips:本次抽奖中奖概率为10%，本次抽奖中奖概率为10%</p>
        <p class="tips">Tips:本次抽奖中奖概率为10%，本次抽奖中奖概率为10%</p>
        <p class="tips">Tips:本次抽奖中奖概率为10%，本次抽奖中奖概率为10%</p>
    </div>
    </div>

</template>

<script>
export default {
    name: 'Index',
    data () {
        return {
            lotteryStart: 0,
            prizeNo: 1,
            prizeNum: 8,
            prizeList: ['200万里通积分', '288元万里通积分红包', '50万里通积分', '10万里通积分', '感谢参与', '88元万里通积分红包', '100万里通积分', '888元万里通积分红包']
        }
    },
    methods: {
        lotteryClick () {
            this.lotteryStart = 1
            let randomNum = 1 + parseInt(Math.random() * this.prizeNum)
            this.prizeNo = randomNum
        },
        lotteryDone (res) {
            console.log(res,'res')
            this.lotteryStart = 0
            let index = res.prizeNo - 1
            console.log(this.prizeList[index])
        }
    }
}

</script>

<style scoped>
.left-box{
    width:50%;
    display:inline-block;
    /* border-right:1px solid #999; */
    height:700px;
    
}
.left-content{
    width:95%;
    margin-left:5%;
}
.wraper{
    margin-left:20px;
    width: 49%;
    display:inline-block;
    /* border:1px solid #afa; */
    margin: 0 auto;
    vertical-align:top;
}
p{
    text-align: left;
    margin-top:20px;
}
.tips{
    /* margin-left:30%; */
    margin-top:10px;
}
input{
    width: 200px;
    height: 30px;
    padding-left: 10px;
}
</style>
<style>
.lottery_wraper{
    max-width:600px;
    margin-left:10%;
}
</style>

