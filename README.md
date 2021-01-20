# LuckDraw
滚动抽奖  

用原生js实现的一个滚动抽奖的插件  
![image](https://github.com/xiaotangren/luck-draw/blob/main/demo.gif)
---

#### 使用方式：

``` javascript

let container = document.getElementById('rolls');
let data = ['智能颈椎按摩仪','智能颈椎按摩仪','飞科吹风机','飞科吹风机','+WIS+面膜','小米体脂称','小米体脂称','小米AI音箱','剃须刀','MAC/魅可口红','充电宝','充电宝','智能扫地机器人','天猫精灵'];

var lucky = new Lucky(container,data,{
    childHeight: 100,
    end: function (item) {
        alert('恭喜获得'+item);
    }
});

document.getElementById('start').addEventListener('click',function () {
    lucky.start();
});

document.getElementById('stop').addEventListener('click',function () {
    lucky.stop();
});
```

#### 参数说明
`new Lucky(container, data, options)`

||type|说明
---|:--:|---:
container|js-dom|容器节点
data|Array|抽奖池数据
options|Object|参数

##### options 说明

||type|默认值|说明
---|:--:|---:|---:
childHeight|Number|200|**子节点的高度(必须配置)**
childRender|Function|`funtion(item){return '<li>{{item}}</li>'}`|渲染子节点的自定义函数
speed|Number|16|运动的速度,帧与帧的间隔
noCss3|Boolean|false|不使用css3进行变换
startIndex|Number|`Math.floor(data.length / 2)`|初始位置
end|Function|null|抽奖结束后的回调函数

#### 参考样式
```css
.luckyBox{
    width: 200px;
    height: 100px;
    position: relative;
    margin-top:100px;
    
}
.rolls{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
.rolls li{
    width: 100%;
    height: 100%;
    line-height: 100px;
    list-style: none;
    font-size: 50px;
    font-weight: bold;
    text-align: center;
}
```
