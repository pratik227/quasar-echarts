<template>
  <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)">
    <q-card-section class="text-h6">
      Doughnut Chart
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts :option="getRadarChartOptions" style="height: 250px;" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "RadarChart",
        components: {
            IEcharts
        },
        computed:{
            getRadarChartOptions(){
                return {
                    tooltip: {},
                    legend: {
                        data: ['Allocated Budget'],
                        show:false
                    },
                    radar: {
                        // shape: 'circle',
                        name: {
                            textStyle: {
                                color: '#fff',
                                // backgroundColor: '#999',
                                borderRadius:3,
                                padding: [3, 5]
                            }
                        },
                        indicator: [
                            {name: 'Sales', max: 6500},
                            {name: 'Administration', max: 16000},
                            {name: 'Information Technology', max: 30000},
                            {name: 'Customer Support', max: 38000},
                            {name: 'Development', max: 52000},
                            {name: 'Marketing', max: 25000}
                        ]
                    },
                    series:
                        [{
                            name: 'Budget vs spending',
                            type: 'radar',
                            // areaStyle: {normal: {}},
                            data: [
                                {
                                    value: [4300, 10000, 28000, 35000, 50000, 19000],
                                    name: 'Allocated Budget'
                                }
                            ],
                            lineStyle:{
                                color:'rgba(0,250,0,0.3)'
                            }
                        }]
                }
            }
        }
    }
</script>

<style scoped>

</style>
