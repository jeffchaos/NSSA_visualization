<template>
  <div id="index" ref="appRef">
    <div class="bg">
      <dv-loading v-if="loading">Loading...</dv-loading>
      <div v-else class="host-body">
        <div class="d-flex jc-center">
          <dv-decoration-10 class="dv-dec-10" />
          <div class="d-flex jc-center">
            <dv-decoration-8 class="dv-dec-8" :color="decorationColor" />
            <div class="title">
              <span class="title-text">网络安全态势感知系统</span>
              <dv-decoration-6
                class="dv-dec-6"
                :reverse="true"
                :color="['#50e3c2', '#67a1e5']"
              />
            </div>
            <dv-decoration-8
              class="dv-dec-8"
              :reverse="true"
              :color="decorationColor"
            />
          </div>
          <dv-decoration-10 class="dv-dec-10-s" />
        </div>

        <!-- 第二行 -->
        <div class="d-flex jc-between px-2">
          <div class="d-flex aside-width">
            <div class="react-left ml-4 react-l-s"  @click="goto1">
              <span class="react-left"></span>
              <span class="text">资产安全态势</span>
            </div>
            <div class="react-left ml-3" @click="goto2">
              <span class="text">态势评估与预测</span>
            </div>
          </div>

          <div class="d-flex aside-width">
            <div class="react-right bg-color-blue mr-3" @click="goto3">
              <span class="text fw-b">流量态势</span>
            </div>
            <div class="react-right mr-4 react-l-s">
              <span class="react-after"></span>
              <span class="text"
                >{{ dateYear }} {{ dateWeek }} {{ dateDay }}</span
              >
            </div>
          </div>
        </div>
        <div id="page1" class="test1" v-if="pageNum===1">
          <div class="d-flex jc-between px-2" style="margin-top:5px;">
          <div class="d-flex aside-width" style="margin-left:60px;">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
                <svg t="1676773340698" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="1875" width="30" height="30"><path d="M768 384h192v256h-192zM64 384h192v256H64zM768 704v64H256v-64H64v188.8A67.2 67.2 0 0 0 131.2 960h761.6a67.2 67.2 0 0 0 67.2-67.2V704h-192zM256 320V256h512v64h192V131.2A67.2 67.2 0 0 0 892.8 64H131.2A67.2 67.2 0 0 0 64 131.2V320h192z" fill="#1296db" p-id="1876"></path></svg>
                <span class="data1" style="margin-left:10px;">{{total.openstackTop }}</span>
                <div>/openstack:{{ total.openstackBottom }}%</div>
              </span>
            </div>
          </div>
          <div class="d-flex aside-width">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
                <svg t="1676776355710" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="3145" width="30" height="30"><path d="M992 787.2H627.2c-12.8-38.4-44.8-70.4-83.2-83.2v-32h281.6c51.2 0 96-44.8 96-96V179.2c0-51.2-44.8-96-96-96H198.4c-51.2 0-96 44.8-96 96v390.4c0 51.2 44.8 96 96 96h281.6v32c-38.4 12.8-70.4 44.8-83.2 83.2H32c-19.2 0-32 12.8-32 32s12.8 32 32 32h364.8c12.8 51.2 57.6 89.6 115.2 89.6s102.4-38.4 115.2-89.6h364.8c19.2 0 32-12.8 32-32s-12.8-25.6-32-25.6zM198.4 147.2h627.2c19.2 0 32 12.8 32 32V448H166.4V179.2c0-12.8 12.8-32 32-32z m-32 422.4V512h691.2v57.6c0 19.2-12.8 32-32 32H198.4c-19.2 0-32-12.8-32-32zM512 876.8c-32 0-57.6-25.6-57.6-57.6s25.6-57.6 57.6-57.6 57.6 25.6 57.6 57.6-25.6 57.6-57.6 57.6z" fill="#1296db" p-id="3146"></path></svg>
                <span class="data1" style="margin-left:10px;">{{ total.middleTop }}</span>
                <div>/中间件:{{ total.middleBottom }}%</div>
              </span>
            </div>
          </div>
          <div class="d-flex aside-width">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
                <svg t="1676776434720" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="6407" width="30" height="30"><path d="M752 960H272c-8.8 0-16-7.2-16-16V96c0-17.7 14.3-32 32-32h448c17.7 0 32 14.3 32 32v848c0 8.8-7.2 16-16 16zM256 0c-35.3 0-64 28.7-64 64v928c0 17.7 14.3 32 32 32h576c17.7 0 32-14.3 32-32V64c0-35.3-28.7-64-64-64H256z" p-id="6408" fill="#1296db"></path><path d="M688 192H336.2c-8.8 0-16-7.2-16-16v-32c0-8.8 7.2-16 16-16H688c8.8 0 16 7.2 16 16v32c0 8.8-7.2 16-16 16zM687.6 320H335.8c-8.8 0-16-7.2-16-16v-32c0-8.8 7.2-16 16-16h351.8c8.8 0 16 7.2 16 16v32c0 8.8-7.2 16-16 16zM639.6 452v56c0 2.2-1.8 4-4 4H387.8c-2.2 0-4-1.8-4-4v-56c0-2.2 1.8-4 4-4h247.8c2.2 0 4 1.8 4 4z m-303.8-68c-8.8 0-16 7.2-16 16v160c0 8.8 7.2 16 16 16h351.8c8.8 0 16-7.2 16-16V400c0-8.8-7.2-16-16-16H335.8zM513.1 845.2H511c-25.7 0-46.6-20.9-46.6-46.6 0-25.7 20.9-46.6 46.6-46.6h2.1c25.7 0 46.6 20.9 46.6 46.6-0.1 25.7-20.9 46.6-46.6 46.6zM512.7 704h-1.4c-17.7 0-32-14.3-32-32s14.3-32 32-32h1.4c17.7 0 32 14.3 32 32s-14.3 32-32 32z" p-id="6409" fill="#1296db"></path></svg>
                <span class="data1" style="margin-left:10px;">{{ total.computerTop }}</span>
                <div>/主机:{{ total.computerBottom }}%</div>
              </span>
            </div>
          </div>
          <div class="d-flex aside-width">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
              <svg t="1676776503992" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="11928" width="30" height="30"><path d="M423.844408 284.113794c-39.870006 0-72.156392 31.870406-72.156392 71.05778 0 39.25137 32.275719 71.05778 72.156392 71.05778 39.838008 0 72.124394-31.80641 72.124394-71.05778C495.968802 315.984201 463.693082 284.113794 423.844408 284.113794zM676.237121 624.651434l20.372314-20.062997c22.558872-22.185558 22.558872-58.183758 0-80.369315l-35.25157-34.686266c11.370098-19.433695 20.244321-40.307318 26.494675-62.439545l38.056764 0c31.870406 0 57.746446-25.438728 57.746446-56.807827l0-28.435911c0-31.369099-25.876039-56.871823-57.746446-56.871823l-37.619452 0c-5.941036-21.812242-14.495275-42.621869-25.556055-61.938236l33.875639-33.310334c22.558872-22.249555 22.558872-58.247755 0-80.369315l-20.372314-20.126994c-22.558872-22.185558-59.122377-22.185558-81.617252 0l-33.246338 32.681033c-20.276319-11.626086-42.216556-20.681633-65.40473-26.931986l0-38.184758C495.968802 25.438728 470.124761 0 438.254354 0l-28.841225 0c-31.870406 0-57.714447 25.438728-57.714447 56.807827l0 38.184758c-23.188174 6.250354-45.117744 15.316567-65.436728 26.931986l-33.182341-32.681033c-22.526874-22.185558-59.090378-22.185558-81.617252 0l-20.404313 20.126994c-22.526874 22.121561-22.526874 58.119761 0 80.369315l33.875639 33.310334c-11.028782 19.316367-19.593687 40.125994-25.534723 61.938236l-37.65145 0C89.834441 284.988418 64.022399 310.480476 64.022399 341.86024l0 28.435911c0 31.369099 25.812042 56.807827 57.714447 56.807827l38.088763 0c6.186358 22.121561 15.092578 42.995183 26.441345 62.439545l-35.219572 34.686266c-22.526874 22.185558-22.526874 58.183758 0 80.369315l20.404313 20.062997c22.526874 22.185558 59.090378 22.185558 81.617252 0l35.432895-34.878256c19.689683 10.996783 40.872623 19.625686 63.186174 25.556055l0 36.435511c0 31.369099 25.844041 56.807827 57.714447 56.807827l28.841225 0c31.870406 0 57.714447-25.438728 57.714447-56.807827l0-36.435511c22.34555-5.941036 43.496492-14.559272 63.154175-25.556055l35.496892 34.878256C617.114744 646.847658 653.678249 646.847658 676.237121 624.651434zM423.844408 513.222339c-87.654284 0-158.744063-70.001833-158.744063-156.237521 0-86.374348 71.089779-156.301518 158.744063-156.301518s158.712064 69.937836 158.712064 156.301518C582.556472 443.231171 511.498692 513.222339 423.844408 513.222339zM931.979001 818.519074l-18.249755 0c-2.879856-10.623469-6.996983-20.681633-12.372714-30.057164l16.372514-16.19119c10.996783-10.751462 10.996783-28.19059 0-38.995383l-9.876839-9.748846c-10.932786-10.751462-28.627902-10.751462-39.624686 0l-16.063197 15.871206c-9.812842-5.621052-20.500308-10.058164-31.689083-13.066014l0-18.495075c0-15.25257-12.564705-27.561289-27.9986-27.561289l-14.004633 0c-15.497892 0-27.9986 12.308718-27.9986 27.561289l0 18.495075c-11.25277 2.997183-21.876239 7.434295-31.753079 13.066014l-16.127194-15.871206c-10.879456-10.751462-28.627902-10.751462-39.560689 0l-9.940836 9.748846c-10.879456 10.815459-10.879456 28.243921 0 38.995383l16.436511 16.19119c-5.311734 9.375531-9.439528 19.433695-12.372714 30.057164L638.926987 818.519074c-15.433895 0-27.9986 12.308718-27.9986 27.561289l0 13.748646c0 15.25257 12.564705 27.561289 27.9986 27.561289l18.495075 0c2.997183 10.751462 7.316967 20.873623 12.810026 30.313151l-17.119144 16.809827c-10.879456 10.751462-10.879456 28.19059 0 38.995383l9.940836 9.684849c10.932786 10.815459 28.681233 10.815459 39.560689 0l17.247138-16.873823c9.503525 5.311734 19.753679 9.503525 30.622469 12.372714l0 17.684449c0 15.188574 12.500708 27.561289 27.9986 27.561289l14.004633 0c15.433895 0 27.9986-12.372714 27.9986-27.561289l0-17.684449c10.751462-2.879856 21.065614-7.06098 30.622469-12.372714l17.119144 16.873823c10.996783 10.815459 28.681233 10.815459 39.624686 0l9.876839-9.684849c10.996783-10.815459 10.996783-28.243921 0-38.995383l-17.065814-16.809827c5.503725-9.439528 9.812842-19.561689 12.810026-30.313151l18.495075 0c15.497892 0 27.9986-12.308718 27.9986-27.561289l0-13.748646C959.977601 830.838458 947.476893 818.519074 931.979001 818.519074zM785.490325 929.20154c-42.557872 0-76.998817-33.939636-76.998817-75.80421s34.440945-75.80421 76.998817-75.80421c42.493875 0 76.998817 33.939636 76.998817 75.80421S827.984201 929.20154 785.490325 929.20154zM785.490325 818.081763c-19.369699 0-34.995583 15.433895-34.995583 34.440945 0 19.06038 15.625886 34.440945 34.995583 34.440945 19.316367 0 34.995583-15.369899 34.995583-34.440945C820.485909 833.515657 804.796027 818.081763 785.490325 818.081763z" fill="#1296db" p-id="11929"></path></svg>
                <span class="data1" style="margin-left:10px;">{{ total.otherTop }}</span>
                <div>/其他设备和系统:{{ total.otherBottom }}%</div>
              </span>
            </div>
          </div>
          <div class="d-flex aside-width">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
               <svg t="1676776544934" class="icon" viewBox="0 0 1190 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="13072" width="30" height="30"><path d="M594.283808 267.286178m-70.145919 0a70.145919 70.145919 0 1 0 140.291839 0 70.145919 70.145919 0 1 0-140.291839 0Z" fill="#1296db" p-id="13073"></path><path d="M1034.098722 715.368289q-5.649252 0-11.198295 0.41336L817.072258 472.763617l145.890986-181.627827a154.333548 154.333548 0 1 0-49.415295-40.822419l-138.663451 172.684222-155.786571-183.920096q-0.638829-0.764089-1.315236-1.4906l-0.200417-0.212943c-0.288099-0.300625-0.576199-0.601251-0.876824-0.88935l-0.876824-0.814194-0.263047-0.237995a31.891341 31.891341 0 0 0-18.388252-7.853838h-0.137786l-1.139871-0.06263H592.091748a31.891341 31.891341 0 0 0-19.578227 8.567823l-0.300625 0.288099c-0.275573 0.263047-0.53862 0.526094-0.801668 0.789142s-0.601251 0.638829-0.901876 0.977032l-0.150313 0.162839q-0.663881 0.751563-1.252605 1.553231L421.950316 425.377543l-147.807473-173.661254a153.832506 153.832506 0 1 0-49.903811 40.246221L381.353365 476.521434 188.915551 719.201263a154.346075 154.346075 0 1 0 59.536349 28.070893l175.239538-220.959645 79.9914 93.945427-0.363256 0.35073 7.515634 9.031287h183.506736c-0.563673-0.638829-1.139871-1.252606-1.71607-1.891435l83.561326-104.066481L956.437169 736.437117a153.957767 153.957767 0 1 0 77.661553-21.068828z m0-650.741188a89.937089 89.937089 0 1 1-89.937089 89.93709 90.037298 90.037298 0 0 1 89.937089-89.93709zM154.76952 244.488754a89.937089 89.937089 0 1 1 89.937089-89.937089 90.037298 90.037298 0 0 1-89.937089 89.937089z m0 714.837022a89.924563 89.924563 0 1 1 89.937089-89.93709 90.037298 90.037298 0 0 1-89.937089 89.924564z m484.031895-366.875684a134.316909 134.316909 0 0 0-77.548819-3.419614l-96.964207-113.899436L595.210736 310.050136l138.788712 163.840826zM1034.098722 959.31325a89.924563 89.924563 0 1 1 89.937089-89.93709 90.037298 90.037298 0 0 1-89.937089 89.93709z" fill="#1296db" p-id="13074"></path><path d="M594.622012 584.834249a134.02881 134.02881 0 1 0 134.02881 134.02881 134.02881 134.02881 0 0 0-134.02881-134.02881z m0 204.174729a70.145919 70.145919 0 1 1 70.145919-70.145919 70.145919 70.145919 0 0 1-70.145919 70.145919z" fill="#1296db" p-id="13075"></path></svg>
                <span class="data1" style="margin-left:10px;">{{ total.dataTop }}</span>
                <div>/大数据:{{ total.dataBottom }}%</div>
              </span>
            </div>
          </div>
          <div class="d-flex aside-width">
            <div class="pane">
              <span class=""></span>
              <span class="" style="text-align:center;line-height:30px;">
                <svg t="1676776586164" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="14316" width="30" height="30"><path d="M719.872 153.6q34.816 0 53.248 9.728t31.744 37.376q5.12 11.264 16.384 34.816t25.6 53.248 29.696 62.976 29.184 62.976 24.576 52.736 14.848 33.28q5.12 11.264 8.704 16.896t6.144 12.288 3.584 15.872 1.024 25.6q0 12.288-0.512 37.888t-0.512 54.272l0 57.344 0 39.936q0 28.672-16.896 48.64t-48.64 19.968l-786.432 0q-29.696 0-45.056-18.944t-16.384-48.64l0-35.84q0-23.552 0.512-50.176t0.512-53.248l0-43.008q0-17.408 0.512-27.648t2.56-17.92 4.608-15.872 7.68-20.48q3.072-8.192 13.312-31.232t24.576-52.736 31.232-63.488 31.744-64 27.136-53.76l16.384-33.792q13.312-26.624 32.768-35.84t46.08-9.216l430.08 0zM897.024 589.824q0-30.72-28.672-30.72l-724.992 1.024q-17.408 0-26.624 9.728t-9.216 25.088l0 145.408q0 12.288 6.656 20.48t20.992 8.192l729.088 1.024q20.48 0 26.624-9.728t6.144-24.064l0-146.432zM293.888 206.848q-14.336 0-24.064 9.728t-9.728 24.064 9.728 24.064 24.064 9.728 23.552-9.728 9.216-24.064-9.216-24.064-23.552-9.728zM215.04 391.168q-14.336 0-24.064 9.728t-9.728 24.064 9.728 24.064 24.064 9.728 24.064-9.728 9.728-24.064-9.728-24.064-24.064-9.728zM686.08 240.64q0 14.336 9.216 24.064t23.552 9.728 24.064-9.728 9.728-24.064-9.728-24.064-24.064-9.728-23.552 9.728-9.216 24.064zM763.904 424.96q0 14.336 9.728 24.064t24.064 9.728 23.552-9.728 9.216-24.064-9.216-24.064-23.552-9.728-24.064 9.728-9.728 24.064zM233.472 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM326.656 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM420.864 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM514.048 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM610.304 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM705.536 740.352l-30.72 0 0-145.408 30.72 0 0 145.408zM795.648 740.352l-30.72 0 0-145.408 30.72 0 0 145.408z" p-id="14317" fill="#1296db"></path></svg>
                <span class="data1" style="margin-left:10px;">{{ total.storeTop }}</span>
                <div>/存储设备:{{ total.storeBottom }}%</div>
              </span>
            </div>
          </div>
        </div>
        <div class="body-box">
          <!-- 第四行数据 -->
          <div class="content-box">
            <div>
              <dv-border-box-12>
                <centerLeft1b />
              </dv-border-box-12>
            </div>
            <div>
              <dv-border-box-13>
                <centerRight1 />
              </dv-border-box-13>
            </div>
            <div>
              <dv-border-box-13>
                <centerRight1b />
              </dv-border-box-13>
            </div>
          </div>

          <!-- 第四行数据 -->
          <div class="bottom-box">
            <dv-border-box-13>
              <bottomLeftb />
            </dv-border-box-13>
            <dv-border-box-12>
              <bottomRightc />
            </dv-border-box-12>
          </div>
        </div>

        </div>
        <div id="page2" v-if="pageNum===2">
          <div class="d-flex ">
            <div class="d-flex">
                <gaugesLeft></gaugesLeft>
          </div>
          <div class="d-flex ">
            <!-- <dv-border-box-13> -->
              <listValue></listValue>
              <!-- </dv-border-box-13> -->
          </div>
          </div>
          <div class="d-flex ">
            <!-- <dv-border-box-13> -->
              <lineCharts></lineCharts>
              <!-- </dv-border-box-13> -->
          </div>
        </div>
        <div id="page3" v-if="pageNum===3">
      
            <div class="d-flex">
            <!-- <dv-border-box-13> -->
              <lineList></lineList>
              <!-- </dv-border-box-13> -->
          </div>
            <div class="d-flex">
              <listShark></listShark>
          </div>
    
     
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import drawMixin from "../utils/drawMixin";
import { formatTime } from '../utils/index.js'
import centerLeft1b from './centerLeft1b'
import centerRight1 from './centerRight1'
import centerRight1b from './centerRight1b'
import bottomLeftb from './bottomLeftb'
import bottomRightc from './bottomRightc'
import gaugesLeft from './page2/centerLeft1b'
import lineCharts from './page2/lineCharts'
import listValue from './page2/centerRight1'
import lineList from './page3/lineCharts'
import listShark from './page3/centerRight1'


export default {
  mixins: [ drawMixin ],
  data() {
    return {
      total:{
        openstackTop:null,
      openstackBottom:null,
      middleTop:null,
      middleBottom:null,
      computerTop:null,
      computerBottom:null,
      otherTop:null,
      otherBottom:null,
      dataTop:null,
      dataBottom:null,
      storeTop:null,
      storeBottom:null,
      },

      pageNum:1,
      timing: null,
      loading: true,
      dateDay: null,
      dateYear: null,
      dateWeek: null,
      weekday: ['周日', '周一', '周二', '周三', '周四', '周五', '周六'],
      decorationColor: ['#568aea', '#000000']
    }
  },
  components: {
    // centerLeft1,
    centerLeft1b,
    // centerLeft2,
    centerRight1,
    centerRight1b,
    
    // centerRight2,
    // center,
    bottomLeftb,
    bottomRightc,
    gaugesLeft,
    lineCharts,
    listValue,
    lineList,
    listShark
  },
  mounted() {
    this.timeFn()
    this.cancelLoading()
    this.getData()
  },
  beforeDestroy () {
    clearInterval(this.timing)
  },
  methods: {
    timeFn() {
      this.timing = setInterval(() => {
        this.dateDay = formatTime(new Date(), 'HH: mm: ss')
        this.dateYear = formatTime(new Date(), 'yyyy-MM-dd')
        this.dateWeek = this.weekday[new Date().getDay()]
      }, 1000)
    },
    cancelLoading() {
      setTimeout(() => {
        this.loading = false
      }, 500)
    },

    goto1(){
      this.pageNum=1
    },
    goto2(){
      this.pageNum=2
    },
    goto3(){
      this.pageNum=3
    },
    getData(){
      this.$axios.get('http://localhost:8080/static/page1.json').then(res=>{
        this.total = res.data.total
      })
    },
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/scss/index.scss';

@font-face {
  font-family: "UnidreamLED";
  src: url(UnidreamLED.eot); /***兼容ie9***/
  src: url(UnidreamLED.eot?#iefix) format("embedded-opentype"),
    /***兼容ie6-ie8***/ url("UnidreamLED.woff") format("woff"),
    local("UnidreamLED"), url("UnidreamLED.woff"); /***默认使用本地的***/
}

.data1{
  color: #ddefff;
  font-size: 40px;
  font-family: "UnidreamLED";
}
.text{
  cursor:pointer;
}
.pane{
  width: 190px;
  height: 100px;
  background:rgba(16, 78, 139, 0.5);
  padding: 20px 10px 5px;
  text-align:center;

}
</style>
