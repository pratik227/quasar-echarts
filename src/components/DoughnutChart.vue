<template>
  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)" >
    <q-card-section class="text-h6">
      Doughnut Chart
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts :option="getDoughnutChartOptions" style="height: 250px;"  :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "DoughnutChart",
        components: {
            IEcharts
        },
        computed:{
            getDoughnutChartOptions() {
                return {
                    tooltip: {
                        trigger: 'item',
                        fontSize:'10px',
                        formatter: "{b}: {c} ({d}%)"
                    },
                    legend: {
                        orient: 'vertical',
                        x: 'right',
                        top:'15%',
                        // data: ['Direct Access', 'Mail Marketing', 'Affiliate Advertising', 'Video ad', 'Search Engine'],
                        textStyle: {
                            color: '#fff'
                        }
                    },
                    grid:{
                      left:'10%'
                    },
                    series: [
                        {
                            type: 'pie',
                            radius: ['50%', '70%'],
                            center:['35%','40%'],
                            avoidLabelOverlap: false,
                            label: {
                                normal: {
                                    show: false,
                                    position: 'center'
                                },
                                emphasis: {
                                    show: true,
                                    textStyle: {
                                        fontSize: '15',
                                        fontWeight: 'bold'
                                    }
                                }
                            },
                            labelLine: {
                                normal: {
                                    show: false
                                }
                            },
                            data: [
                                {
                                    value: 335, name: 'Direct access',
                                    itemStyle: {
                                        color: '#828fc9'
                                    }
                                },
                                {
                                    value: 310, name: 'Mail Marketing', itemStyle: {
                                        color: '#558b2f'
                                    }
                                },
                                {
                                    value: 234, name: 'Affiliate Advertising',
                                    itemStyle: {
                                        color: '#b0bec5'
                                    }
                                },
                                {
                                    value: 135, name: 'Video ad',
                                    itemStyle: {
                                        color: '#02a9f4'
                                    }
                                },
                                {
                                    value: 1548, name: 'Search Engine',
                                    itemStyle: {
                                        color: '#c33f5c'
                                    }
                                }
                            ]
                        }
                    ]
                }
            }
        }
    }
</script>

<style scoped>

</style>
