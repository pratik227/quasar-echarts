<template>
  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)">
    <q-card-section class="text-h6">
      Horizontal Bar Chart
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts style="height: 250px;" :option="getHorizontalBarChartOptions" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "HorizontalBarChart",
        components: {
            IEcharts
        },
        computed:{
            getHorizontalBarChartOptions() {
                return {
                    tooltip: {
                        trigger: 'axis',
                    },
                    legend: {
                        data: ['Direct Access', 'Mail Marketing', 'Affiliate Advertising','Search Engine'],
                        textStyle: {
                            color: '#fff'
                        }
                    },
                    grid: {
                        left: '3%',
                        right: '4%',
                        bottom: '3%',
                        containLabel: true
                    },
                    xAxis: {
                        type: 'value',
                        axisLabel: {
                            textStyle: {
                                color: '#fff'
                            }
                        },
                        splitLine:{
                            show:false
                        }
                    },
                    yAxis: {
                        type: 'category',
                        data: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday'],
                        axisLabel: {
                            textStyle: {
                                color: '#fff'
                            }
                        }
                    },
                    series: [
                        {
                            name: 'Direct Access',
                            type: 'bar',
                            stack: 'Total',
                            label: {
                                normal: {
                                    show: false,
                                    position: 'insideRight'
                                }
                            },
                            data: [320, 302, 301, 334, 390],
                            color:'#ea4b64'
                        },
                        {
                            name: 'Mail Marketing',
                            type: 'bar',
                            stack: 'Total',
                            label: {
                                normal: {
                                    show: false,
                                    position: 'insideRight'
                                }
                            },
                            data: [120, 132, 101, 134, 90],
                            color:'#1e88e5'
                        },
                        {
                            name: 'Affiliate Advertising',
                            type: 'bar',
                            stack: 'Total',
                            label: {
                                normal: {
                                    show: false,
                                    position: 'insideRight'
                                }
                            },
                            data: [220, 182, 191, 234, 290],
                            color:'#90a4ae'
                        },
                        {
                            name: 'Search Engine',
                            type: 'bar',
                            stack: 'Total',
                            label: {
                                normal: {
                                    show: false,
                                    position: 'insideRight'
                                }
                            },
                            data: [820, 832, 901, 934, 1290],
                            color:'#f9982d'
                        }
                    ]
                }
            }
        }
    }
</script>

<style scoped>

</style>
