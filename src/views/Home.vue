<template>
<v-app id="inspire" :style="{background: $vuetify.theme.themes.dark.background}">
  <SideBar />
  <v-container>
    <v-row>
      <v-col cols="12" sm="12">
        <v-card
     class="mx-auto rounded-xl"
      height="620px"
      elevation-2
      color="grey darken-4"
       >
        <v-row>
          <v-col cols="12" sm="12">
            <v-toolbar flat color="rgba(0,0,0,0)" dark>
              <v-toolbar-title>Dashboard</v-toolbar-title>
              <v-spacer></v-spacer>
            <v-btn outlined class="">
              <v-icon right class="mr-2">fas fa-sliders-h</v-icon>
              Filters
            </v-btn>
            </v-toolbar>
            
          </v-col>
          <v-col cols="12" sm="4">
            
            <v-card class="cardOr mx-2 rounded-xl mt-n7" elevation="16">
              <v-row>
                <v-col cols="12" sm="8">
                  <v-list-item three-line>
                    <v-list-item-content>
                      <div class="mb-4">
                        <v-btn tile fab color="orange" elevation="0">
                          <v-icon color="">fab fa-btc</v-icon>
                        </v-btn>
                      </div>
                      <v-list-item-title class="headline mb-1 white--text">
                        $1200
                      </v-list-item-title>
                      <v-list-item-subtitle class="white--text">45% This Week</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                  <v-avatar size="100" class="ml-n10 mt-6" tile>
                    <v-img src="lineO.png"></v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-card>
         
          </v-col>
          <v-col cols="12" sm="4">
             <v-card class="cardVr mx-2 rounded-xl mt-n7" elevation="16">
              <v-row>
                <v-col cols="12" sm="8">
                  <v-list-item three-line>
                    <v-list-item-content>
                      <div class="mb-4">
                        <v-btn tile fab color="teal" elevation="0">
                          <v-icon color="">fab fa-ethereum</v-icon>
                        </v-btn>
                      </div>
                      <v-list-item-title class="headline mb-1 white--text">
                        $232.40
                      </v-list-item-title>
                      <v-list-item-subtitle class="white--text">35% This Week</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                  <v-avatar size="100" class="ml-n10 mt-6" tile>
                    <v-img src="lineV.png"></v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-card>
         
          </v-col>
          <v-col cols="12" sm="4">
             <v-card class="cardR mx-2 rounded-xl mt-n7" elevation="16">
              <v-row>
                <v-col cols="12" sm="8">
                  <v-list-item three-line>
                    <v-list-item-content>
                      <div class="mb-4">
                        <v-btn tile fab color="#6e0b14" elevation="0">
                          <v-icon color="">fas fa-lira-sign</v-icon>
                        </v-btn>
                      </div>
                      <v-list-item-title class="headline mb-1 white--text">
                        600
                      </v-list-item-title>
                      <v-list-item-subtitle class="white--text">21% This Week</v-list-item-subtitle>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
                <v-col cols="12" sm="4">
                  <v-avatar size="100" class="ml-n10 mt-6" tile>
                    <v-img src="line.png"></v-img>
                  </v-avatar>
                </v-col>
              </v-row>
            </v-card>
         
          </v-col>
          <v-col cols="12" sm="8">
           
               <v-toolbar flat color="rgba(0,0,0,0)" dark>
              <v-toolbar-title>Market Overview</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn outlined >Weekly (2020)
              <v-icon right  class="mr-2" >fas fa-chevron-down</v-icon> 
            </v-btn>
            </v-toolbar>
           <v-sparkline
    :value="value"
    :smooth="radius || false"
    :padding="padding"
    :line-width="width"
    :stroke-linecap="lineCap"
    :fill="fill"
    :type="type"
    :auto-line-width="autoLineWidth"
    auto-draw
    color="white"
  ></v-sparkline>
  <v-divider color="white" class="mx-4"></v-divider>
  <v-toolbar flat color="rgba(0,0,0,0)" dark>
              <v-toolbar-title>Recent Activities</v-toolbar-title>
            </v-toolbar>
            <v-row>
              <v-col cols="12" sm="2">
                <v-btn fab class="ml-5 mt-n2" color="grey lighten-1" small>
                  <v-icon>fas fa-long-arrow-alt-up</v-icon></v-btn>
              </v-col>
              <v-col cols="12" sm="2"><span class="white--text">Bitcoin</span></v-col>
              <v-col cols="12" sm="2"><span class="white--text">10:42:23 AM</span></v-col>
              <v-col cols="12" sm="2"><span class="white--text">+1545,00</span></v-col>
              <v-col cols="12" sm="2"><span class="white--text">Completed</span></v-col>
            </v-row>
          </v-col>
           <v-col cols="12" sm="4">
             <v-card class=" mx-2 rounded-xl" elevation="8" color="teal">
               <v-toolbar flat color="rgba(0,0,0,0)" dark>
              <v-toolbar-title>Sell Order</v-toolbar-title>
              <v-spacer></v-spacer>
            
              <v-icon  class="mr-2" small>fas fa-ellipsis-v</v-icon>

            </v-toolbar>
             <v-simple-table class="teal" dark>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">
            Price
          </th>
          <th class="text-left">
            Amount
          </th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="item in orders"
          :key="item.name"
        >
          <td>{{ item.price }}</td>
          <td>{{ item.amount }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
            </v-card>
         
          </v-col>
        </v-row>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</v-app>
</template>

<script>
  import SideBar from '../components/SideBar'

  export default {
    name: 'Home',
 data () {
      return {
        width: 2,
      radius: 10,
      padding: 8,
      lineCap: 'round',
      value: [0, 2, 5, 9, 5, 10, 3, 5, 0, 0, 1, 8, 2, 9, 0],
      fill: false,
      type: 'trend',
      autoLineWidth: false,
        orders: [
          {
            price: 89.03,
            amount: 0.15,
          },
          {
            price: 94.03,
            amount: 0.18,
          },
           {
            price: 92.03,
            amount: 0.22,
          },
           {
            price: 94.03,
            amount: 0.18,
          },
           {
            price: 33.03,
            amount: 0.19,
          },
        ],
      }
    },
    components: {
      SideBar,
    },
  }
</script>
<style scoped>
.cardOr{
background: rgb(1,1,1);
background: linear-gradient(90deg, rgba(1,1,1,1) 0%, rgba(34,34,29,1) 70%, rgba(135,115,12,1) 100%);
}
.cardVr{
  background: rgb(1,1,1);
background: linear-gradient(90deg, rgba(1,1,1,1) 0%, rgba(29,34,30,1) 70%, rgba(19,158,112,1) 100%);
}
.cardR{
  background: rgb(1,1,1);
background: linear-gradient(90deg, rgba(1,1,1,1) 0%, rgba(74,36,36,1) 70%, rgba(158,19,19,1) 100%);
}
</style>
