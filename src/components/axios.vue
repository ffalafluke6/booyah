<template>
<div>
     <body background="https://cdn.wallpapersafari.com/60/78/BMUQl0.jpg">
          <b-row>
               <img
                    src="https://static.displate.com/857x1200/displate/2018-10-05/3d0bed4c15c897827abbac5a4e816e5f_1fe2fbd2755921fac40b6013add2d0bc.jpg"
                    alt
                    height="200"
                    width="250"
                    border="0"
                    align="center"
                    hspace="40"
               />
          </b-row>

          <u>
               <h1 align="center" class="text-white">High-speed stream (HSS)</h1>
          </u>

          <div class="container">
               <br />
               <br />
               <div group="center">
                    <b-row cols-lg="5">
                         <b-card
                              bg-variant="dark"
                              v-for="user in userList"
                              :key="user.results"
                              title
                              img-src="https://i.pinimg.com/originals/99/63/e9/9963e99a67e9423150f1adf8546f80a8.jpg"
                              img-alt
                              img-top
                              tag="article"
                              style="max-width: 20rem;"
                              class="ms-1"
                              color="dark"
                              align="center"
                         >
                              {{ user.hssID }}
                              {{ user.note }}
                              <a
                                   :href="user.link"
                              >
                                   <br />
                                   <br />
                                   <b-button gradient="aqua">More</b-button>
                              </a>
                         </b-card>
                    </b-row>
               </div>
          </div>
     </body>
</div>
</template>
   
<script>
import axios from "axios";
export default {
     data() {
          return {
               userList: null,
          };
     },
     mounted() {
          let url = "https://api.nasa.gov/DONKI/HSS?startDate=yyyy-MM-dd&endDate=yyyy-MM-dd&api_key=DEMO_KEY";
          axios
               .get(url)
               .then((response) => {
                    this.userList = response.data;
               })
               .catch();
          (err) => {
               console.log(err);
          };
     },
};
</script>

<style>
.ms-1 {
     margin-bottom: 50px !important;
     margin-right: 50px !important;
}
.h1 {
     color: #2c3e50;
}

</style>
   