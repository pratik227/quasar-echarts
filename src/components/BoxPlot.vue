<template>

  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)">
    <q-card-section class="text-h6">
      Box Plot
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts style="height: 250px;" :option="getBoxChartOptions" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "BoxPlot",
        components: {
            IEcharts
        },
        computed:{
            getBoxChartOptions() {
                return {
                    tooltip: {
                        trigger: 'item',
                        axisPointer: {
                            type: 'shadow'
                        }
                    },
                    grid:{
                        top:'10%',
                        bottom:'15%',
                        left:'8%',
                        right:'5%'
                    },
                    xAxis: {
                        type: 'category',
                        data: ['Prod1', 'Prod2', 'Prod3', 'Prod4', 'Prod5'],
                        boundaryGap: true,
                        nameGap: 30,
                        splitArea: {
                            show: false
                        },
                        axisLabel: {
                            formatter: '{value}',
                            color:'#fff'
                        },
                        splitLine: {
                            show: false
                        },
                        scale: true
                    },
                    yAxis: {
                        type: 'value',
                        splitArea: {
                            show: false
                        },
                        scale: true,
                        axisLabel: {
                            color:'#fff'
                        }

                    },
                    series: [
                        {
                            name: 'boxplot',
                            type: 'boxplot',
                            data: [[655, 850, 940, 980, 1070], [760, 800, 845, 885, 960], [780, 840, 855, 880, 940], [720, 767.5, 815, 865, 920], [740, 807.5, 810, 870, 950]],
                            tooltip: {
                                formatter: function (param) {
                                    return [
                                        'Experiment ' + param.name + ': ',
                                        'upper: ' + param.data[5],
                                        'Q3: ' + param.data[4],
                                        'median: ' + param.data[3],
                                        'Q1: ' + param.data[2],
                                        'lower: ' + param.data[1]
                                    ].join('<br/>');
                                }
                            },
                            itemStyle: {
                                color: {
                                    type: "linear",
                                    x: 0,
                                    y: 0,
                                    x2: 0,
                                    y2: 1,
                                    colorStops: [{"offset": 0, "color": "#aeea35"}, {"offset": 1, "color": "red"}],
                                    global: false
                                }
                            },
                        }
                    ]
                }
            }
        }
    }
</script>

<style scoped>

</style>
