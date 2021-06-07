# v-charts使用总结

柱状图

```html
<ve-histogram 
          ref="histogram"
          :data="bugRankData" 
          :grid="grid" 
          :loading="loading.bugRankLoading"
          :data-empty="dataEmpty.bugRankEmpty"
          :settings="bugRankSetting"
          :extend="bugRankExtend" 
          :height="height">
        </ve-histogram> 
```

```js
      grid:{
        top: 45,
        bottom: 30,
        right: "30",
      },图的位置
      extend: {
        xAxis: {
          axisLabel: {
              //过滤X轴数据的显示
            formatter: (params) => {
              return this.$dayjs(params).format("YYYY-MM");
            }
          }
        },
        yAxis: {
          minInterval: 1,	//y轴的数据分割刻度都是整数
        }
        
      },
      legend: {
        show: true,
        top: "5%",
      },	//修改图表中图例的位置，与上方的距离可使用%，也可使用像素
      series : [
　　　　　　{
　　　　　　　　name: yTitle[i],
　　　　　　　　type:echartsType[i],
　　　　　　　　itemStyle:{
　　　　　　　　　　normal:{
　　　　　　　　　　　　label: {
　　　　　　　　　　　　　　show: true,//是否在图上展示数据
　　　　　　　　　　　　　　// position:'top',//数据在柱状图顶部显示
　　　　　　　　　　　　　　textStyle:{
　　　　　　　　　　　　　　　　color:'#000000' //数据颜色
　　　　　　　　　　　　　　},
　　　　　　　　　　　　　　formatter: '{c}' //显示百分比
　　　　　　　　　　　　　}
　　　　　　　　　　　　},
　　　　　}],
        xAxis: {
　　　　　　axisLabel: { 
　　　　　　　　interval:0,　　//强制显示X轴所有标签 设置为1则 隔一个标签,显示一个标签
　　　　　　　　rotate: 40,　　//文字倾斜角度
　　　　　　}
　　　　}
```

