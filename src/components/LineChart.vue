<template>
  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)">
    <q-card-section class="text-h6">
      Line Chart
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts style="height: 250px;" :option="getLineChartOptions" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "LineChart",
        components: {
            IEcharts
        },
        computed:{
            getLineChartOptions(){
                return {
                    tooltip: {
                        trigger: 'axis'
                    },
                    legend: {

                        data: ['Mail Marketing', 'Affiliate Advertising', 'Video Advertising'],
                        textStyle:{
                            color:'#fff'
                        }
                    },
                    grid: {
                        left: '3%',
                        right: '4%',
                        bottom: '3%',
                        containLabel: true
                    },
                    xAxis: {
                        type: 'category',
                        boundaryGap: false,
                        data: ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'],
                        axisLabel: {
                            textStyle: {
                                color: '#fff'
                            }
                        },
                    },
                    yAxis: {
                        type: 'value',
                        axisLabel: {
                            textStyle: {
                                color: '#fff'
                            }
                        },
                    },
                    series:
                        [
                            {
                                name: 'Mail Marketing',
                                type: 'line',
                                stack: 'Total',
                                data: [120, 132, 101, 134, 90, 230, 210],
                                color:'#f9982d'
                            },
                            {
                                name: 'Affiliate Advertising',
                                type: 'line',
                                stack: 'Total',
                                data: [220, 182, 191, 234, 290, 330, 310],
                                color:'#42a5f5'
                            },
                            {
                                name: 'Video Advertising',
                                type: 'line',
                                stack: 'Total',
                                data: [150, 232, 201, 154, 190, 330, 410],
                                color:'#689f38'
                            }
                        ]
                }
            }
        }
    }
</script>

<style scoped>

</style>
