<template>
  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #55EAF7 10%, #977dbe 100%)" >
    <q-card-section class="text-h6">
      Gauge
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts :option="getGaugeChartOptions" style="height: 105px;" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "GaugeChart",
        components: {
            IEcharts
        },
        props: {
            bgColor: {
                // default: '#2B2D3E'
                default: 'linear-gradient( 135deg, #343E59 10%, #2B2D3E 40%)'
            }
        },
        computed:{
            getGaugeChartOptions(){
                return {
                    tooltip: {
                        formatter: "{a} <br/>{b} : {c}%"
                    },
                    title: {
                        text:'68% New Visitors',
                        left: 'center',
                        textStyle: {
                            fontSize: 18,
                        },
                        bottom:'12%'
                    },
                    axisLine: {
                        show: true,
                    },
                    grid:{
                        top:'25%',
                    },
                    series:{
                            name: '',
                            type: 'gauge',
                            min: 0,
                            radius:'100%',
                            max: 100,
                            startAngle:180,
                            endAngle:0,
                            axisTick: {
                                show: false
                            },
                            axisLabel: {
                                show: false
                            },
                            splitLine: {
                                show: false
                            },
                        pointer: {
                            width: 3,
                            show: false
                        },
                        axisLine: {
                            show: true,
                            lineStyle: {
                                color: [[0.68 , '#293c55'], [1, '#ddd']],
                                width: 20
                            }
                        },
                        detail: {
                            offsetCenter: [5, '-10%'],
                            textStyle: {
                                fontWeight: 'bolder',
                            },
                            show:false
                        },
                        data: [{'value': 0.68 , "name": ''}]
                    }


                }
            }
        }
    }
</script>

<style scoped>

</style>
