<!--
 * @Author: xpy
 * @Description: 
 * @Date: 2021-06-10 20:10:24
 * @LastEditTime: 2021-06-11 15:11:34
-->
<script>
  import * as echarts from 'echarts';
  // resize()
  export default {
    name:'A',
    mounted(){
      const dom = document.getElementById('chartsA');
      const myChart = echarts.init(dom);
      console.log(`myChart`, myChart)
      const option = {
        title:{
          text:"柱形图-就业行业",
          left: "center",
          textStyle: {
            fontSize: ".275rem",
            color:"#ffffff",
            textShadowColor: "rgba(255, 0, 0, 1)",
            textShadowBlur: 10,
            textShadowOffsetX: 2,
            textShadowOffsetY: 2
          },
        },
        // 横坐标轴
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'],
          axisLabel: {  // 横坐标轴刻度标签的相关设置。
            show: true,   // 是否显示
            textStyle: {  // 字体样式在这里改变
              color: '#fff',
              fontSize: ".125rem"
            },
            interval:0
          },
        },
        yAxis: {
            type: 'value',
            offset: 0,
            axisLabel: {  // 横坐标轴刻度标签的相关设置。
              // show: true,   // 是否显示
              textStyle: {  // 字体样式在这里改变
                fontSize: ".125rem"
              },
              interval:0
            },
        },
        tooltip:{},
        // 数据列表
        series: [{
            data: [120, 200, 150, 80, 70, 110, 130],
            type: 'bar'
        }],
        grid: {
          show: false,
          left: 0,
          top: 40,
          right: "10px",
          bottom: 0,
          containLabel: true,
        }
      };
      myChart.setOption(option);
    },
    render:function(){
      return <div id="chartsA"></div>
    },
  }
</script>

<style scoped>
#chartsA{
  height: 3.5rem;
}
</style>