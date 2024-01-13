<template>
  <div>
    <h2>Question 4</h2>
    <Line :data="data" :options="options" />
    <table border="1">
      <thead>
        <tr>
          <th></th>
          <th>평균 기온</th>
          <th>평균 습도</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[0]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[0]" /></td>
        </tr>
        <tr>
          <td>2월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[1]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[1]" /></td>
        </tr>
        <tr>
          <td>3월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[2]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[2]" /></td>
        </tr>
        <tr>
          <td>4월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[3]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[3]" /></td>
        </tr>
        <tr>
          <td>5월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[4]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[4]" /></td>
        </tr>
        <tr>
          <td>6월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[5]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[5]" /></td>
        </tr>
        <tr>
          <td>7월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[6]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[6]" /></td>
        </tr>
        <tr>
          <td>8월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[7]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[7]" /></td>
        </tr>
        <tr>
          <td>9월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[8]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[8]" /></td>
        </tr>
        <tr>
          <td>10월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[9]" />
          </td>
          <td><input type="number" placeholder="습도" v-model="humid[9]" /></td>
        </tr>
        <tr>
          <td>11월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[10]" />
          </td>
          <td>
            <input type="number" placeholder="습도" v-model="humid[10]" />
          </td>
        </tr>
        <tr>
          <td>12월</td>
          <td>
            <input type="number" placeholder="기온" v-model="temperature[11]" />
          </td>
          <td>
            <input type="number" placeholder="습도" v-model="humid[11]" />
          </td>
        </tr>
      </tbody>
    </table>
    <button @click="randomNumber">random</button>
  </div>
</template>

<script>
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
} from "chart.js";

import { Line } from "vue-chartjs";

ChartJS.register(
  CategoryScale,
  LinearScale,
  BarElement,
  Title,
  Tooltip,
  Legend,
  PointElement,
  LineElement
);
export default {
  components: {
    Line,
  },
  computed: {
    data() {
      return {
        labels: [
          "1월",
          "2월",
          "3월",
          "4월",
          "5월",
          "6월",
          "7월",
          "8월",
          "9월",
          "10월",
          "11월",
          "12월",
        ],
        datasets: [
          {
            label: "평균 기온",
            backgroundColor: "blue",
            data: Object.assign([], this.temperature),
          },
          {
            label: "평균 습도",
            backgroundColor: "red",
            data: Object.assign([], this.humid),
          },
        ],
      };
    },
    options() {
      return {
        responsive: true,
        // maintainAspectRatio: false,
      };
    },
  },
  data() {
    return {
      loaded: false,
      temperature: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
      humid: [0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0],
    };
  },
  methods: {
    randomNumber() {
      //       function getRandom(min, max)
      // {
      // 	return Math.floor(Math.random() * (max - min + 1) + min);
      // }
      this.temperature = this.temperature.map(() =>
        Math.floor(Math.random() * (30 - 1 + 1) + 1)
      );
      this.humid = this.humid.map(() =>
        Math.floor(Math.random() * (100 - 1 + 1) + 1)
      );
    },
  },
};
</script>
<style scoped></style>
