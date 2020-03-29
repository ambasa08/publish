<template lang="html">
  <div id="app">
    <div class="head">
      <p class="time">2020-03-14 12:00:00</p>
    </div>
    <div class="content-container">
      <div v-for="(item, idx) in machine" :key="idx">
        <div class="content-top">
          <div class="f_mname">
            {{ item.mid }}
          </div>
          <div class="f_p">
            {{ item.process }}
          </div>
        </div>
        <div class="content-mid">
          <div class="f_end">
            {{ item.timer }}
          </div>
        </div>
        <div class="progress">
          <progress
            class="sb-progress sb-progress--green"
            value="30"
            max="100"
          />
          <div class="progress-text">
            <div class="progress-count">{{ item.count }}</div>
            <div class="progress-time">{{ item.fTime }}</div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- <v-app id="inspire">
	    <v-row no-gutters />
	    <v-card color="black" width="100%">
	      <div style='text-align:center'>
	        <span class="time">2020-03-14 12:00:00</span>
	      </div>
	    </v-card>
	    <v-responsive width="100%" />
      <div v-for="item in machine">
        <v-col :key="item.idx">
          <v-card>
            <v-row>
              <v-toolbar dense flat color="#b5b5b5" height="120">
                <span class="f_mname">{{item.mid}}</span>
                  <v-spacer></v-spacer>
                <span class="f_p">{{item.process}}</span>
              </v-toolbar>
	            </v-row>
	            <div class="text-center">
	              <span class="f_end" style="align:center">{{item.timer}}</span>
	            </div>
	      	    <v-footer :fixed="true" height="100" absolute class="white">
	              <v-row>
	                <v-progress-linear value="15" height="94"
                  color="#357d21" background-color="#828282" rounded>
                  <v-flex style="maxWidth:20px"></v-flex>
                  <span class="vt">{{ item.count}}</span>
                  <v-spacer></v-spacer>
                  <span class="vt">
                    <div class="text-right">{{ item.fTime }}</div>
                  </span>
                  <v-flex style="maxWidth:20px"></v-flex>
	                </v-progress-linear>
	              </v-row>
	            </v-footer>
          </v-card>
        </v-col>
      </div>
  	</v-app> -->
</template>

<script>
export default {
  // el: '#app',
  //vuetify: new Vuetify(),
  data() {
    return {
      //tab: null,
      machine: [
        {
          mid: "Puma280",
          idx: 1,
          process: "CS98D25H49-01-2",
          timer: "가공완료",
          count: "100/100",
          fTime: "0 시간 6 분"
        },
        {
          mid: "PumaV400",
          idx: 2,
          process: "O0229",
          timer: "04:34",
          count: "4/100",
          fTime: "84 시간 40 분"
        },
        {
          mid: "Lynx220C",
          idx: 3,
          process: "D580007-02-F",
          timer: "01:33",
          count: "459/500",
          fTime: "2 시간 36 분"
        },
        {
          mid: "Puma240",
          idx: 4,
          process: "WGR150D35H24-02-1",
          timer: "00:10",
          count: "70/100",
          fTime: "1 시간 31 분"
        },
        {
          mid: "Lynx220CL",
          idx: 5,
          process: "CS98D25H49-02-02",
          timer: "02:34",
          count: "12/100",
          fTime: "5 시간 0 분"
        },
        {
          mid: "Lynx220SY",
          idx: 6,
          process: "JIG-CD",
          timer: "READY",
          count: "110/200",
          fTime: "23 시간 48 분"
        }
      ]
    };
  }
};
</script>

<style scoped>
.time {
  font-size: 20px;
  text-align: center;
}
.f_mname {
  font-size: 20px;
}
.f_p {
  font-size: 20px;
}
.vt {
  font-size: 20px;
}
.f_end {
  font-size: 20px;
}
.progress {
  position: relative;
  display: flex;
}
.progress progress {
  width: 100%;
  height: 30px;
}
.progress .progress-text {
  position: absolute;
  top: 0;
  left: 0;
  display: flex;
  justify-content: space-between;
  width: 100%;
}
.progress-count,
.progress-time {
  line-height: 30px;
}
</style>
