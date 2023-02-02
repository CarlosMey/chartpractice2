<template>
  <div class="first__part">
    <img src="../assets/Bannerr.png" alt="">
    <div class="first__part-words">
      <div class="first__part-words-left">
        <span>21°</span>

        <span>Mumbai, India</span>
      </div>

      <div class="first__part-words-right">
        <span>03:11 PM</span>

        <span>Monday</span>
      </div>
    </div>
  </div>
  <div class="second__part">
    <div class="second__part-left">
      <div class="second__part-left-up">
        <div class="second__part-left-up-boxes">
          <div class="second__part-left-up-boxes-uno">
            <img src="../assets/hot.png" alt="">
          </div>
          <div class="second__part-left-up-boxes-dos">
            <span class="humidity">Humidity</span>
            <span class="">56%</span>
          </div>
        </div>
        <div class="second__part-left-up-boxes border">
          <div class="second__part-left-up-boxes-uno">
            <img src="../assets/cloudy.png" alt="">
          </div>
          <div class="second__part-left-up-boxes-dos">
            <span class="sunrise">Sunrise</span>
            <span class="">6:45 AM</span>
          </div>
        </div>
        <div class="second__part-left-up-boxes ">
          <div class="second__part-left-up-boxes-uno">
            <img src="../assets/foggy.png" alt="">
          </div>
          <div class="second__part-left-up-boxes-dos">
            <span class="air-quality">Air Quality</span>
            <span class="">151</span>
          </div>
        </div>
        <div class="second__part-left-up-boxes border">
          <div class="second__part-left-up-boxes-uno">
            <img src="../assets/sunrise.png" alt="">
          </div>
          <div class="second__part-left-up-boxes-dos">
            <span class="sunset">Sunset</span>
            <span class="">6:15 PM</span>
          </div>
        </div>
      </div>
      <div class="second__part-left-down">
        <div class="second__part-left-down-boxes">
          <div class="second__part-left-down-boxes-left">
            <span class="monthly-rainfall">Monthly Rainfall</span>
          </div>
        </div>
        <div class="second__part-left-down-boxes">
          <div class="second__part-left-down-boxes-right">
            <span class="this-year">This year</span>
          </div>
        </div>
        <div class="second__part-left-down-boxes">
          <div class="second__part-left-down-boxes-left">
            <span class="mm">22mm</span>
          </div>
        </div>
        <div class="second__part-left-down-boxes">
          <div class="second__part-left-down-boxes-right">
            <span class="dos">+2%</span>
          </div>
        </div>
      </div>
    </div>
    <div class="second__part-right">
      <BarChart class="BarChart"/>
      <div class="second__part-right-days">
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>{{data.grados}}</span>
        </div>
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
        <div class="second__part-right-days-boxes">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
        <div class="second__part-right-days-boxes no-border">
          <span>Mon</span>
          <img src="../assets/cold.png" alt="">
          <span>19°</span>
        </div>
      </div>
    </div>
    

  </div>

  
</template>

<script>

import Chart from 'chart.js/auto';
import BarChart from './BarChart.vue';
import jsonData from '../jsonData.json'

export default {
    name: "HelloWorld",
    components:{ BarChart},
    data(){
      return{
        data:jsonData
      }
    },
    mounted() {
        console.log("Mounted");
        const ctx = document.getElementById("myChart");
        const myChart = new Chart(ctx, {
            type: "bar",
            data: {
                labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
                datasets: [{
                        label: "# of Votes",
                        data: [12, 19, 3, 5, 2, 3],
                        backgroundColor: [
                            "rgba(255, 99, 132, 0.2)",
                            "rgba(54, 162, 235, 0.2)",
                            "rgba(255, 206, 86, 0.2)",
                            "rgba(75, 192, 192, 0.2)",
                            "rgba(153, 102, 255, 0.2)",
                            "rgba(255, 159, 64, 0.2)"
                        ],
                        borderColor: [
                            "rgba(255, 99, 132, 1)",
                            "rgba(54, 162, 235, 1)",
                            "rgba(255, 206, 86, 1)",
                            "rgba(75, 192, 192, 1)",
                            "rgba(153, 102, 255, 1)",
                            "rgba(255, 159, 64, 1)"
                        ],
                        borderWidth: 2
                    }]
            },
            options: {
                scales: {
                    y: {
                        beginAtZero: true
                    }
                }
            }
        });
        myChart;
    }, 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>

.first__part{
  display: flex;
  width: 50%;
  justify-content: center;
  margin: auto;
  text-align: center;
  &-words{
    position: absolute;
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    &-left{
      flex-direction: row;
      left: 20%;
      align-items: center;
      margin-top: 170px;
      margin-right: 300px;
      flex-direction: column;
      justify-content: center;
      display: flex;
    }
    &-right{
      flex-direction: row;
      left: 20%;
      align-items: center;
      margin-top: 170px;
      flex-direction: column;
      justify-content: center;
      display: flex;
    }
  }
}

.first__part img{
  position: relative;
  display: flex;
  margin: auto;
  border-radius: 10px;
}

.second__part{
  display: flex;
  width: 50%;
  justify-content: center;
  margin: auto;
  text-align: center;
  flex-wrap: wrap;
  flex-direction: row;
  &-left{
    margin-right: 50px;
    margin-top: 20px;
    display: inline-block;
    &-up{
      padding-top: 20px;
      padding-bottom: 20px;
      display:flex;
      flex-direction:row;
      flex-wrap:wrap;
      justify-content:center;
      align-content:flex-start;
      height: 170px;
      width: 300px;
      border-radius: 5px;
      box-shadow: 2px 2px 10px 5px rgba(0, 0, 0, 0.2);
      margin-bottom: 50px;
      background-color: white;
      &-boxes{
        height: 80px;
        width: 140px;
        flex-direction: row;
        display: flex;
        justify-content: center;
        align-items: center;
      }
    }
    &-down{
      display:flex;
      flex-direction:row;
      flex-wrap:wrap;
      justify-content:center;
      align-content:flex-start;
      height: 180px;
      width: 300px;
      border-radius: 5px;
      box-shadow: 2px 2px 10px 5px rgba(0, 0, 0, 0.2);
      margin-bottom: 50px;
      padding-top: 20px;
      background-image: linear-gradient(135deg, #d1fff8 0, #befff6 10%, #a7fff4 20%, #8dfff3 30%, #6cfbf2 40%, #3cf2f2 50%, #00e8f3 60%, #00dff5 70%, #00d6f9 80%, #00cefd 90%, #00c6ff 100%);
      &-boxes{
        height: 80px;
        width: 140px;
        margin: 0px;
        flex-direction: row;
        display: flex;
        justify-content: center;
        align-items: center;
        &-left{
          padding-right: 30px;
        }
        &-right{
          padding-left: 30px;
        }
      }
    }
  }
  &-right{
    margin-top: 20px;
    display: inline-block;
    box-shadow: 2px 2px 10px 5px rgba(0, 0, 0, 0.2);
    border-radius: 5px;
    height: 460px;
    background-color: white;
    &-days{
      display:flex;
      flex-direction:row;
      flex-wrap:wrap;
      justify-content:center;
      align-content:flex-start;
      width: 400px;
      &-boxes{
        width: 40px;
        padding-top: 4px;
        padding-bottom: 4px;
        padding-right: 6px;
        padding-left: 6px;
        align-self:auto;
        height:auto;
        border-right: 1px solid black;
      }
    }
  }
}
.second__part-left-up-boxes span{
  display: flex;
}
.second__part-left img{
  width: 50px;
  height: 50px;
}
.second__part-right-days-boxes img{
  width: 30px;
  height: 30px;
}
.border{
  border-left: 1px solid black;
}
.no-border{
  border-right: none;
}
.humidity, .air-quality, .sunrise, .sunset {
  font-size: 12px;
}
.monthly-rainfall, .this-year{
  font-size: 13px;
}
.mm{
  font-size: 30px;
}
.dos{
  font-size: 30px;
  color: blue;
}

</style>
