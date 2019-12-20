<template>
    <q-card class="q-pa-sm text-white" style="background:linear-gradient( 135deg, #3A6073 25%, #2c343c 80%)">
    <q-card-section class="text-h6">
      Stack Bar
    </q-card-section>
    <q-card-section class="q-pa-none q-pt-md">
      <IEcharts style="height: 250px;" :option="getStackBarOptions" :resizable="true"></IEcharts>
    </q-card-section>
  </q-card>
</template>

<script>
    import IEcharts from 'vue-echarts-v3/src/full.js';

    export default {
        name: "StackBarChart",
        components: {
            IEcharts
        },
        computed:{
            getStackBarOptions() {
                return {
                    tooltip: {
                        trigger: 'axis',
                        axisPointer: {// coordinate axis indicator, coordinate axis trigger is valid
                            type: 'shadow' // default is a straight line, optional: 'line' | 'shadow'
                        }
                    },
                    legend: {
                        data: ['Mail Marketing', 'Affiliate Advertising', 'Video ad'],
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
                        type: 'category',
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
                                type: 'bar',
                                stack: 'Advertisement',
                                data: [120, 132, 101, 134, 90, 230, 210],
                                color:'#4dd0e1'
                            },
                            {
                                name: 'Affiliate Advertising',
                                type: 'bar',
                                stack: 'Advertisement',
                                data: [220, 182, 191, 234, 290, 330, 310],
                                color:'#f9982d'
                            },
                            {
                                name: 'Video ad',
                                type: 'bar',
                                stack: 'Advertisement',
                                data: [150, 232, 201, 154, 190, 330, 410],
                                color:'#77909c'
                            }
                        ]
                }
            }
        }
    }
</script>

<style scoped>

</style>
