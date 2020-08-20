# ### 使用步骤如下：

##### 1. 将需要的文件下载到本地

下载地址：https://github.com/jiang-diama/WeChart-echarts

或者直接克隆：https://github.com/jiang-diama/WeChart-echarts.git

##### 2.将下载好文件放到一个文件夹中如，components文件夹

##### 3.在需要用到Echarts图表的页面文件中的`.json` 配置文件中约会Echarts

```json
{
  "usingComponents": {
    "ec-canvas": "../../components/ec-canvas/ec-canvas"
  }
}
```

##### 4. 在页面的`js`文件中引入：

```js
import * as echarts from '../../components/ec-canvas/echarts';
```

##### 5. 以上步骤完成后，接下来就是编写代码搞配置了：

- 5.1 ：**定义一个全局变量：**

  ```
  let chart;
  ```

- 5.2 : **在data对象中声明一个存放echarts数据的对象`echart`并初始化数据:**

  ```js
  data{
  	echart: {
        onInit: function (canvas, width, height) {
          chart = echarts.init(canvas, null, {
            width: width,
            height: height
          })
          canvas.setChart(chart);
          chart.setOption(getOption());
          return chart;
        }
      }
  }
  ```

- 5.3 : **在Page外配置Echarts图表，用官方简单的例子演示**

  ```js
  function getOption() {
    return {
      title: {
         text: 'ECharts 入门示例'
       },
       tooltip: {},
       legend: {
         data:['销量']
       },
       xAxis: {
         data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
       },
       yAxis: {},
       series: [{
          name: '销量',
          type: 'bar',
          data: [5, 20, 36, 10, 10, 20]
       }]
    }
  }
  ```

- 5.4 : **将定义好的echarts图表引入到页面中**

  ```html
  <view class="ec-week">
  	<ec-canvas ec="{{ echart }}"></ec-canvas>
  </view>
  ```

##### 6. 注意： `ec-week`类要设置宽高才能生效。

##### 7. 本文件中已包含所有的Echarts图表已供你使用，如果担心文件的体积过大可以到官方网站下载自己的项目需求下载所需要的，然后替换掉文件夹中的`echarts.js`文件即可。

##### 8. 官方下载地址：

https://echarts.apache.org/zh/builder.html



