<template>
  <div>
    <Header />
    <div class="min-h-screen">
      <div class="main">
        <div class="main__graphic wrapper" id="wrapper">
          <div class="img-wrapper">
            <img width="100%" id="img-1" :src="land_1" alt="" />
            <img width="100%" id="img-2" :src="back" alt="" />
            <img width="100%" id="img-3" :src="front" alt="" />
            <img width="100%" id="img-4" :src="land_2" alt="" />
            <img width="100%" id="img-5" :src="front_dark" alt="" />
            <img width="100%" id="img-6" :src="back_dark" alt="" />
          </div>
          <div class="lottiebox" v-if="index == 4">
            <lottie-animation
              ref="anim"
              :animationData="require('@/assets/lottie/story_postit.json')"
              :loop="true"
              :autoPlay="true"
            />
          </div>
        </div>
        <Scrollama
          class="scrollama-content"
          :debug="true"
          :offset="0.5"
          @step-enter="handler"
        >
          <div class="step flex-column" data-step-no="1">
            <h2 class="header-2 font-weight-bold text-center">
              งบ อบจ. <br />
              สำคัญกับชีวิตเราอย่างไร?
            </h2>
            <img :src="arrowdown" id="arrowdown" alt="" />
          </div>
          <div class="step" data-step-no="2">
            <div class="text-1 text-step-2 text-center">
              <b>องค์กรปกครองส่วนท้องถิ่น หรือ อบจ.</b> <br />
              <p class="m-0 text-1">
                เป็นองค์กรปกครองส่วนท้องถิ่นที่มีขนาดใหญ่ที่สุด
                และมีเขตพื้นที่รับผิดชอบครอบคลุมทั่วทั้งจังหวัดก่อตั้งขึ้นเพื่อจัดหาบริการสาธารณประโยชน์ต่าง
                ๆ ให้แก่ประชาชนในแต่ละจังหวัด
              </p>
            </div>
          </div>
          <div class="step" data-step-no="3">
            <div class="text-step-3">
              <p class="text-1 font-weight-bold text-center">
                อบจ. มีอำนาจหน้าที่ครอบคลุม หลากหลายด้าน ไม่ว่าจะเป็น...
              </p>

              <div
                class="random header-3"
                id="random"
                @mouseover="clearTimer"
                @mouseleave="setTimer"
              >
                วิศวกรรมจราจร
              </div>
            </div>
          </div>
          <div class="step" data-step-no="4">
            <div class="text-1 text-step-2 text-center">
              นั่นหมายความว่า... <br />
              โครงสร้างพื้นฐาน สวัสดิการ รวมถึงกิจกรรมต่าง ๆ ภายใน อบจ.
              ที่ช่วยให้เราใช้ชีวิตในเมืองได้อย่างมีความสุข ล้วนเกี่ยวข้องกับ<b
                >งบประมาณขององค์การบริหารส่วนจังหวัด (อบจ.)</b
              >
              การใช้เงินของ อบจ.
              จึงเป็นตัวแปรสำคัญที่มีส่วนในการกำหนดคุณภาพชีวิตของผู้คน
            </div>
          </div>
          <div class="step align-items-start" data-step-no="5">
            <div class="text-step-3 mt-5">
              <h5 class="header-5 font-weight-bold text-center mb-5">
                จึงเป็น<span class="blue-a">สิทธิและหน้าที่</span
                >ของประชาชนอย่างเราที่จะต้องเข้าไปมีส่วนร่วมแสดงความคิดเห็นในขั้นตอนการจัดสรรงบในแต่ละปี
              </h5>
            </div>
          </div>
        </Scrollama>
      </div>
      <div class="">
        <div class="story-header-box">
          <div class="d-none d-lg-flex justify-content-between px-5 pt-3">
            <div class="circle"></div>
            <div class="circle"></div>
          </div>
          <div class="story-intro">
            <div class="header header-3 white-b">
              พวกเรามีสิทธิเข้าไปมีส่วนร่วม<br class="d-none d-sm-inline" />
              ทั้งขั้นตอนก่อนและหลังการจัดสรรงบ
            </div>
          </div>
        </div>
        <div
          class="story-intro-2 px-2 d-flex flex-column flex-lg-row justify-content-center align-items-center"
        >
          <div
            class="position-relative story-intro-content-1 d-flex justify-content-end"
          >
            <div>
              <div
                class="circle bg-orange-a text-2 d-flex justify-content-center align-items-center text-center font-weight-bold"
              >
                ก่อน<br />จัดสรรงบ
              </div>
              <div class="desc mt-3 mt-lg-0">
                <p class="text-2 text-center">
                  เราเรียกขั้นตอนนี้ว่า
                  <span class="orange-a">Participatory Budgeting</span>
                  แต่ในความเป็นจริง
                  สำหรับประเทศไทยแนวคิดการจัดสรรงบประมาณแบบมีส่วนร่วมลักษณะนี้อาจยังไม่ประสบความสำเร็จ
                  หรือเห็นภาพได้ชัดเนื่องจากข้อจำกัดหลายอย่าง
                </p>
              </div>
            </div>
          </div>
          <div class="mx-3 arrow-box">
            <img width="100%" :src="arrow" class="arrow" alt="" />
          </div>
          <div class="position-relative story-intro-content-2">
            <div>
              <div
                class="circle bg-light-blue text-2 d-flex justify-content-center align-items-center text-center font-weight-bold"
              >
                หลัง<br />จัดสรรงบ
              </div>
              <div class="desc mt-3 mt-lg-0">
                <p class="text-2 text-center">
                  อย่างไรก็ตาม หลังจากที่การจัดสรรงบประมาณเสร็จสิ้นไปแล้ว
                  ประชาชนอย่างเรา ๆ ก็ยังคงมีบทบาทสำคัญ นั่นก็คือการ
                  <span class="light-blue">ติดตาม ตรวจสอบ</span>
                  เพื่อให้มั่นใจว่างบเหล่านั้น ถูกใช้แบบที่ควรจะเป็น
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-blue-a overflow-hidden">
        <div class="d-none d-lg-flex justify-content-between px-5 pt-3">
          <div class="circle"></div>
          <div class="circle"></div>
        </div>
        <p class="text-center white-b text-1 py-5 px-2">
          แต่ในความเป็นจริงแล้ว... <br />
          การสำรวจงบของ อบจ. ก็ไม่ได้ง่ายอย่างที่ควรจะเป็น
        </p>
        <div class="position-relative papertear">
          <img
            :src="papertear_m"
            alt=""
            width="100%"
            class="d-none d-lg-block"
          />
          <img :src="papertear" alt="" width="100%" class="d-block d-lg-none" />
          <h2 class="header-2 text-center m-0">
            อุปสรรคที่ทำให้การสำรวจงบ อบจ. <br />
            ยังคงเป็นเรื่องสุดหินสำหรับบ้านเรา
          </h2>
        </div>
        <div class="bg-papertear">
          <div class="wrapper-box">
            <div class="position-relative text-center paper-1">
              <img
                width="100%"
                :src="obstacle1"
                alt=""
                class="d-none d-sm-block"
              />
              <img
                width="100%"
                :src="obstacle1_m"
                alt=""
                class="d-block d-sm-none"
              />
              <div class="content">
                <div>
                  <h5 class="header-5 font-weight-bold">
                    ข้อจำกัดด้านโครงสร้าง
                  </h5>
                  <p class="text-2">
                    <span class="blue-a">
                      โครงสร้างงบฯ
                      มีความซับซ้อนยากต่อการทำความเข้าใจของประชาชนทั่วไป</span
                    >
                    มีหลายแหล่งที่มาของงบประมาณ
                    นอกเหนือจากองค์กรปกครองส่วนท้องถิ่น
                  </p>
                </div>
              </div>
            </div>
            <div class="position-relative text-center">
              <img
                width="100%"
                :src="obstacle2"
                alt=""
                class="d-none d-sm-block"
              />
              <img
                width="100%"
                :src="obstacle2_m"
                alt=""
                class="d-block d-sm-none"
              />
              <div class="content">
                <div>
                  <h5 class="header-5 font-weight-bold">
                    ข้อจำกัดด้านการเปิดเผยข้อมูล
                  </h5>
                  <p class="text-2">
                    <span class="blue-a"
                      >ข้อมูลที่ภาครัฐนำเสนอยังกระจัดกระจาย
                      โดยไม่มีหน่วยงานกลางที่รวบรวมข้อมูลไว้แหล่งเดียว</span
                    >
                    หน่วยงานต้นทาง (อบจ.) เปิดเผยข้อมูลไม่ครบถ้วน
                    <span class="blue-a"
                      >ข้อมูลที่เปิดเผยไม่เป็นไปตามมาตรฐานของการเปิดเผยข้อมูลสากล
                      คือไม่เป็น Machine-readable มีแต่เพียงไฟล์ .pdf
                      หรือภาพเท่านั้น ซึ่งทำให้ไม่สามารถนำไปใช้งานต่อได้</span
                    >
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="bg-black world-bg px-2">
        <div class="d-none d-lg-flex justify-content-between p-5">
          <div class="circle"></div>
          <div class="circle"></div>
        </div>

        <h4 class="header-4 font-weight-bold white-a text-center pt-5">
          การตรวจสอบงบของภาครัฐไทย<span class="lime-b">ยังคงทำได้ยาก</span>
          <br class="d-none d-sm-inline" />
          งั้นเรามาดูกันดีกว่า ว่าต่างประเทศเขาจัดการเรื่องนี้อย่างไรบ้าง
        </h4>
        <p
          class="text-2 text-center white-a py-5 content-box d-none d-lg-block"
        >
          เพื่อความโปร่งใส
          หลายประเทศได้มีการนำข้อมูลเกี่ยวกับการจัดสรรงบประมาณของภาครัฐมาเผยแพร่ให้ประชาชนทั่วไปได้รับรู้
          และสามารถนำข้อมูลเหล่านั้นมาวิเคราะห์ต่อยอด
          หรือแม้กระทั่งเปลี่ยนให้เป็นชาร์ตรูปแบบต่าง ๆ
          ที่ประชาชนสามารถกดสำรวจเองได้
        </p>

        <div
          class="square-box-wrapper d-flex d-lg-block pb-0 pb-lg-5 pt-5 pt-lg-0"
        >
          <div class="d-flex justify-content-around pb-5">
            <div class="bg-blue-a square-box white-a square-box-1">
              <h2 class="header-2 font-weight-light">สหรัฐอเมริกา</h2>
              <ul class="text-2">
                <li>
                  มีหน้า<span class="font-weight-bold">เว็บไซต์ของภาครัฐ</span>
                  ที่แปลงรายงานงบประมาณ<span class="font-weight-bold"
                    >มาอยู่ในรูปชาร์ต Treemap</span
                  >
                </li>
                <li>
                  กดสำรวจ และดาวน์โหลดข้อมูลได้ โดยสามารถดูรายละเอียด
                  แยกย่อยได้ถึงรายไตรภาค
                </li>
              </ul>
              <div class="link-box-white">
                <a
                  class="header-5 white-a link-white d-flex justify-content-between"
                  href="https://www.usaspending.gov/"
                  target="_blank"
                >
                  usaspending.gov <img :src="link_white" alt="" />
                </a>
              </div>
            </div>

            <div class="bg-yellow square-box square-box-2">
              <h2 class="header-2 font-weight-light">สหราชอาณาจักร</h2>
              <ul class="text-2">
                <li>เผยแพร่ผ่านเว็บไซต์ทางการของรัฐ</li>
                <li>ทั้งในรูปแบบ PDF HTML รวมถึง Excel Spreadsheet</li>
                <li>
                  สามารถส่งคำร้องขอเอกสารงบ ใน format ต่าง ๆ
                  ด้วยโปรแกรมหรือเทคโนโลยีรูป<span class="nowrap">แบบ</span>อื่น
                  ๆ
                </li>
              </ul>
              <div class="link-box-black">
                <a
                  class="header-5 black link-black d-flex justify-content-between"
                  href="https://www.gov.uk/"
                  target="_blank"
                >
                  gov.uk<img :src="link_black" alt="" />
                </a>
              </div>
            </div>
          </div>

          <div class="d-block d-lg-flex justify-content-around">
            <div class="bg-purple-b square-box white-a square-box-3">
              <h2 class="header-2 font-weight-light">ประเทศบราซิล</h2>
              <ul class="text-2">
                <li>
                  Portal da Transparência แปลงข้อมูลงบประมาณของรัฐ
                  ให้กลายเป็นชาร์ตรูปร่าง หน้าตาต่าง ๆ
                </li>
                <li>
                  จัดสร้างขึ้นเพื่อต้องการส่งเสริม <b> ความโปร่งใส</b>
                  และลดการคอร์รัปชันในรัฐบาล
                </li>
              </ul>
              <div class="link-box-white">
                <a
                  class="header-5 white-a link-white d-flex justify-content-between"
                  href="https://transparencia.gov.br/"
                  target="_blank"
                >
                  transparencia.gov.br<img :src="link_white" alt="" />
                </a>
              </div>
            </div>

            <div class="box-4 d-none d-lg-block">
              <img :src="graph" width="100" alt="" />
              <img :src="money" class="money" width="100" alt="" />
              <img :src="coin" class="coin" width="100" alt="" />
            </div>
          </div>
        </div>
        <div class="text-right d-block d-lg-none">
          <img :src="drag_papertear" alt="" />
        </div>

        <p
          class="text-2 text-center white-a py-5 content-box d-block d-lg-none"
        >
          เพื่อความโปร่งใส
          หลายประเทศได้มีการนำข้อมูลเกี่ยวกับการจัดสรรงบประมาณของภาครัฐ
          มาเผยแพร่ให้ประชาชนทั่วไปได้รับรู้
          และสามารถนำข้อมูลเหล่านั้นมาวิเคราะห์ต่อยอด
          หรือแม้กระทั่งเปลี่ยนให้เป็นชาร์ตรูปแบบต่าง ๆ
          ที่ประชาชนสามารถกดสำรวจเองได้
        </p>
      </div>
      <div class="story-header-box">
        <div>
          <div class="text-center">
            <img
              :src="thailand_arrow"
              alt=""
              class="d-none d-lg-block mx-auto"
            />
            <img
              :src="thailand_arrow_m"
              alt=""
              class="d-block d-lg-none mx-auto"
            />
          </div>
          <b-col class="position-relative text-center th-box mt-3">
            <img :src="thailand" width="500" alt="" class="d-none d-lg-block" />
            <img
              :src="thailand_m"
              alt=""
              width="500"
              class="d-block d-lg-none mx-auto"
            />
            <div class="intro-text white-a text-left">
              <h2 class="header-2 font-weight-light">กลับมาที่บ้านเรา...</h2>
              <p class="text-2">
                การสำรวจตรวจสอบงบประมาณภาครัฐดูจะเป็นเรื่องยาก
                เพราะการอ่านเอกสาร <b>PDF หลายร้อยหน้า</b>
                เป็นภาระที่หนักหนาสำหรับประชาชนทั่วไป
              </p>
            </div>
          </b-col>
        </div>
      </div>
      <div
        class="bg-lime h-100vh symbol-wrapper d-flex justify-content-center align-items-center"
      >
        <div>
          <div
            class="bg-blue-a white-a symbol-header header-4 font-weight-bold text-center mb-5"
          >
            แต่เรามีข่าวดี!!
          </div>
          <p class="mb-0 text-1 text-center">
            <b> องค์กรต่อต้านคอร์รัปชัน (ประเทศไทย)</b> ได้ทำการ<span
              class="orange-a"
              >แปลงข้อมูลงบประมาณ อบจ.</span
            >
            ที่มีการเผยแพร่มาไว้ในรูปแบบที่เราทุกคนสามารถตรวจสอบได้แล้ว
          </p>
        </div>
      </div>
      <div class="bg-grid-blue text-center px-3">
        <div class="bg-black text-1 white-a grid-header">
          หากยังไม่มีธงในใจว่าต้องการเจาะจงตรวจสอบตรงจุดไหน
          อาจเริ่มจากการไล่ดูงบประมาณที่เกี่ยวข้องกับความเป็นอยู่ของเราก่อน เช่น
        </div>
      </div>
      <div class="work-category text-center">
        <div class="box text-1 bg-white-a blue-a boxleft">
          งานป้องกันและบรรเทาสาธารณภัย
        </div>
        <hr class="m-0" />
      </div>
      <div class="work-category text-center">
        <div class="box text-1 bg-white-a blue-a boxright">งานโรงพยาบาล</div>
        <hr class="m-0" />
      </div>
      <div class="work-category text-center">
        <div class="box text-1 bg-white-a blue-a boxleft">งานด้านการศึกษา</div>
        <hr class="m-0" />
      </div>
      <div class="work-category text-center">
        <div class="box text-1 bg-white-a blue-a boxright">
          งานก่อสร้าง สะพาน ถนน เส้นทางจราจร
        </div>
        <hr class="m-0" />
      </div>
      <div class="work-category text-center">
        <div class="box text-1 bg-white-a blue-a boxleft">
          งานสวัสดิการสังคม
        </div>
        <hr class="m-0" />
      </div>
      <div
        class="h-100vh choose-wrapper d-flex flex-column justify-content-between"
      >
        <div
          class="px-3 d-flex justify-content-center align-items-center h-100"
        >
          <div>
            <div class="header-box mb-5">
              <div class="content bg-blue-a">
                <p class="text-1 font-weight-bold m-0 white-a">
                  คลิกเลือก เพื่อไปต่อ
                </p>
              </div>
            </div>
            <div class="d-flex flex-column flex-lg-row justify-content-center">
              <NuxtLink to="/dashboard">
                <div class="box-1 pointer mx-3">
                  <h4 class="header-4 blue-a ml-4 mb-3 font-weight-bold">
                    ตรวจสอบ<br />งบประมาณ<br />ในจังหวัดของคุณ
                  </h4>
                </div>
              </NuxtLink>
              <NuxtLink to="/conclusion">
                <div class="box-2 pointer mx-3 mt-3 mt-lg-0">
                  <h4 class="header-4 white-a ml-4 mb-3 font-weight-bold">
                    สรุปภาพรวมงบ อบจ.
                  </h4>
                </div>
              </NuxtLink>
            </div>
          </div>
        </div>
        <div class="gradient"></div>
      </div>
    </div>
  </div>
</template>

<script>
const INTERVAL = 5000;

import "intersection-observer";
import Scrollama from "vue-scrollama";
import * as story_postit_lottie from "~/assets/lottie/story_postit.json";
import Lottie from "vue-lottie/src/lottie.vue";
import LottieAnimation from "lottie-web-vue";

export default {
  components: {
    Scrollama,
    Lottie,
    LottieAnimation,
  },
  data() {
    return {
      story_postit: story_postit_lottie,
      index: 0,
      logo: require("~/assets/images/logo.svg"),
      arrow: require("~/assets/images/arrow.svg"),
      arrowdown: require("~/assets/images/arrowdown.svg"),
      papertear: require("~/assets/images/papertear.svg"),
      obstacle1: require("~/assets/images/obstacle1.svg"),
      obstacle2: require("~/assets/images/obstacle2.svg"),
      papertear_m: require("~/assets/images/papertear_m.svg"),
      obstacle1_m: require("~/assets/images/obstacle1_m.svg"),
      obstacle2_m: require("~/assets/images/obstacle2_m.svg"),
      coin: require("~/assets/images/coin.svg"),
      money: require("~/assets/images/money.svg"),
      graph: require("~/assets/images/graph.svg"),
      thailand_arrow: require("~/assets/images/thailand_arrow.svg"),
      thailand: require("~/assets/images/thailand.svg"),
      thailand_arrow_m: require("~/assets/images/thailand_arrow_m.svg"),
      thailand_m: require("~/assets/images/thailand_m.svg"),
      link_white: require("~/assets/images/link_white.svg"),
      link_black: require("~/assets/images/link_black.svg"),
      land_1: require("~/assets/images/land_1.png"),
      land_2: require("~/assets/images/land_2.png"),
      back: require("~/assets/images/back.png"),
      back_dark: require("~/assets/images/back_dark.png"),
      front: require("~/assets/images/front.png"),
      front_dark: require("~/assets/images/front_dark.png"),
      drag_papertear: require("~/assets/images/drag_papertear.svg"),
      currStep: null,
      word_random: [
        { title: "ป้องกันและระงับโรคติดต่อ ", bg: "#253472", color: "#FFFEF5" },
        {
          title: "การจัดการ และดูแลสถานีขนส่งทางบกและทางน้ำ ",
          bg: "#FFB930",
          color: "#181F1C",
        },
        {
          title: "กำจัดขยะมูลฝอย สิ่งปฏิกูล และน้ำเสีย ",
          bg: "#89E26A",
          color: "#181F1C",
        },
        { title: "วิศวกรรมจราจร  ", bg: "#FFFFFF", color: "#181F1C" },
        {
          title: "ป้องกันและบรรเทาสาธารณภัย ",
          bg: "#F2A8EE",
          color: "#181F1C",
        },
        {
          title: "ส่งเสริมประชาธิปไตย ความเสมอภาคและสิทธิเสรีภาพของประชาชน",
          bg: "#E0FD6A",
          color: "#181F1C",
        },
        { title: "ส่งเสริมการท่องเที่ยว ", bg: "#A80C7C", color: "#FFFEF5" },
        {
          title: "ดูแลทรัพยากรธรรมชาติและสิ่งแวดล้อม ",
          bg: "#EC6440",
          color: "#FFFEF5",
        },
        {
          title: "การพัฒนาคุณภาพชีวิต เด็กสตรี คนชรา และผู้ด้อยโอกาส ",
          bg: "#F2A8EE",
          color: "#181F1C",
        },
        { title: "ส่งเสริมการกีฬา ", bg: "#E0FD6A", color: "#181F1C" },
      ],
      isFirstTime: true,
      img2: "",
      img3: "",
      timer: null,
    };
  },
  mounted() {
    var width = window.screen.width;

    if (width > 768) {
      this.img2 = 0;
      this.img3 = 0;
    } else if (width > 600) {
      this.img2 = 30;
      this.img3 = 15;
    }

    document.getElementsByTagName("body")[0].style.overflow = "hidden";
    document.getElementById("img-1").style.bottom = 0;
    setTimeout(() => {
      document.getElementById("img-2").style.bottom =
        width > 600 ? 50 - this.img2 + "px" : "15px";
    }, 1000);
    setTimeout(() => {
      document.getElementById("img-3").style.bottom =
        width > 600 ? 40 - this.img3 + "px" : "10px";
      document.getElementById("arrowdown").style.opacity = 1;
      document.getElementsByTagName("body")[0].style.overflow = "unset";
      this.isFirstTime = false;
    }, 2000);

    this.setTimer();
  },
  methods: {
    clearTimer() {
      clearInterval(this.timer);
    },
    setTimer() {
      clearInterval(this.timer);
      var i = 1;

      this.timer = setInterval(() => {
        document.getElementById("random").textContent =
          this.word_random[i].title;
        document.getElementById("random").style.background =
          this.word_random[i].bg;
        document.getElementById("random").style.color =
          this.word_random[i].color;
        i = ++i % this.word_random.length;
      }, 2000);
    },
    handler({ element, index, direction }) {
      var width = window.screen.width;
      this.index = index;
      if (index == 0) {
        if (!this.isFirstTime) {
          document.getElementById("img-2").style.transform = "none";
          document.getElementById("img-3").style.transform = "none";
          document.getElementById("img-2").style.bottom =
            width > 600 ? 50 - this.img2 + "px" : "15px";
          document.getElementById("img-3").style.bottom =
            width > 600 ? 40 - this.img3 + "px" : "10px";
        }
      } else if (index == 1) {
        document.getElementById("img-2").style.transform = "scale(2)";
        document.getElementById("img-3").style.transform = "scale(2.5)";
        document.getElementById("img-2").style.bottom =
          width > 600 ? 155 - this.img2 + "px" : "50px";
        document.getElementById("img-3").style.bottom =
          width > 600 ? 85 - this.img3 + "px" : "30px";
      }

      if (index == 4) {
        document.getElementById("img-1").style.opacity = 0;
        document.getElementById("img-2").style.opacity = 0;
        document.getElementById("img-3").style.opacity = 0;
        document.getElementById("img-4").style.opacity = 1;
        document.getElementById("img-5").style.opacity = 1;
        document.getElementById("img-6").style.opacity = 1;
        document.getElementById("wrapper").classList.add("wrapper-grid");
      } else {
        document.getElementById("img-4").style.opacity = 0;
        document.getElementById("img-5").style.opacity = 0;
        document.getElementById("img-6").style.opacity = 0;
        document.getElementById("img-1").style.opacity = 1;
        document.getElementById("img-2").style.opacity = 1;
        document.getElementById("img-3").style.opacity = 1;
        document.getElementById("wrapper").classList.remove("wrapper-grid");
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.wrapper {
  background-image: url("~/assets/images/sky.png");
  background-size: cover;
}

.wrapper-grid {
  background-image: url("~/assets/images/bg_grid_blue.svg");
  background-size: contain;
}

.bg-grid-blue {
  background: url("~/assets/images/bg_grid_tile.svg"), #0056a6;
  padding: 105px 0;
  background-size: 20px;

  .grid-header {
    padding: 10px;
    max-width: 576px;
    margin: auto;
  }
}

.world-bg {
  background-image: url("~/assets/images/globe.png");
  background-size: 600px;
  background-position: center;
  background-repeat: no-repeat;
}

.symbol-wrapper {
  background-image: url("~/assets/images/bg_symbol.svg");
  background-size: 450px;
  background-position: center;
  background-repeat: no-repeat;

  @media #{$mq-mini-mobile} {
    background-size: 100px;
    padding: 0 10px;
  }

  p {
    margin: auto;
    max-width: 500px;
  }
}

.main__graphic {
  position: sticky;
  top: 0;
  height: 100vh;
  color: rgba($color: #000000, $alpha: 0.1);
  font-size: 10rem;
  overflow: hidden;
  // display: flex;
  // align-items: flex-end;
  // justify-content: center;

  img {
    position: absolute;
    bottom: -100%;
    transition: 0.7s;
    left: 0;
    right: 0;
  }
}

#img-2 {
  max-width: 964px;
  margin: auto;
}

#img-3 {
  max-width: 647px;
  margin: auto;
}

#img-4 {
  max-width: 964px;
  margin: auto;
  transform: scale(2.5);
  bottom: 0;
  z-index: 5;
  transition: 0.5s;
  opacity: 0;
}

#img-5 {
  max-width: 647px;
  margin: auto;
  transform: scale(3);
  bottom: 130px;
  z-index: 5;
  transition: 0.5s;
  opacity: 0;

  @media #{$mq-small-laptop} {
    transform: scale(2.5);
    bottom: 115px;
  }
  @media #{$mq-mobile} {
    transform: scale(3);
    //bottom: 11%;
  }
  @media #{$mq-mini-mobile} {
    bottom: 50px;
  }
}

#img-6 {
  max-width: 946px;
  margin: auto;
  transform: scale(2);
  bottom: 190px;
  z-index: 5;
  transition: 0.5s;
  opacity: 0;

  @media #{$mq-small-laptop} {
    transform: scale(2);
    bottom: 185px;
  }

  @media #{$mq-mobile} {
    transform: scale(2);
    bottom: 150px;
  }
  @media #{$mq-mini-mobile} {
    bottom: 60px;
  }
}
.step {
  padding: 15vh 10px;
  width: 100%;
  height: 100vh;
  margin: auto;
  display: flex;
  align-items: center;
  justify-content: center;
}

.scrollama-content {
  position: relative;
  z-index: 1;
  margin-top: -100vh;
}

.text-step-2 {
  margin: auto;
  width: 600px;
  background: white;
  padding: 16px;
}

.text-step-3 {
  margin: auto;
  width: 600px;
}

.random {
  padding: 20px 64px;
  text-align: center;
  font-weight: lighter;
  width: fit-content;
  margin: auto;

  @media #{$mq-mobile} {
    padding: 10px;
  }
}
.story-intro {
  padding: 30px 10px 66px;
  text-align: center;

  @media #{$mq-mobile} {
    padding: 30px 10px;
  }

  .header {
    max-width: 838px;
    margin: auto;
    border-top: 2px solid #ffffff;
    border-bottom: 2px solid #ffffff;
    padding: 25px 0;
  }
}

.circle {
  width: 27px;
  height: 27px;
  border-radius: 50%;
  border: 1px solid #fffef5;
}

.story-intro-2 {
  padding: 60px 0;
  background-image: url("~/assets/images/bg_grid_blue.svg");

  @media #{$mq-lg} {
    background: #0056a6;
  }

  .story-intro-content-1,
  .story-intro-content-2 {
    flex: 0 0 48%;
  }

  .story-intro-content-1 .circle {
    right: 75px;
    position: relative;

    @media #{$mq-lg} {
      position: unset !important;
    }
  }

  .story-intro-content-2 .desc {
    left: 75px;
    position: relative;

    @media #{$mq-lg} {
      position: unset;
    }
  }

  .arrow-box {
    flex: 0 0 2%;
  }

  .circle {
    width: 154px;
    height: 154px;
    border-radius: 50%;
    border: none !important;

    @media #{$mq-lg} {
      margin: auto;
      width: 98px;
      height: 98px;
      color: #fffef5;
    }
  }

  .arrow {
    @media #{$mq-lg} {
      transform: rotate(90deg);
    }
  }

  .desc {
    max-width: 400px;
    position: relative;
    bottom: 40px;

    @media #{$mq-small-laptop} {
      left: 50px;
    }
    @media #{$mq-lg} {
      position: unset;
      color: #fffef5 !important;
      span {
        color: #fffef5 !important;
        font-weight: bold;
      }
    }
  }
}

.papertear {
  position: absolute;
  width: 100%;
  bottom: 10%;

  h2 {
    position: absolute;
    bottom: 10px;
    width: 100%;

    @media #{$mq-mobile} {
      font-size: 40px;
    }

    @media #{$mq-mini-mobile} {
      font-size: 20px;
    }
  }
}

.bg-papertear {
  background: #ecfea6;
  margin-top: -100px;
  @media #{$mq-mini-mobile} {
    margin-top: 0;
  }
  .wrapper-box {
    max-width: 1280px;
    margin: auto;

    .content {
      position: absolute;
      width: 100%;
      display: flex;
      top: 0;
      justify-content: center;
      align-items: center;
      height: 100%;
      padding: 0 10px;
      p {
        max-width: 700px;

        @media #{$mq-mini-mobile} {
          font-size: 12px !important;
          max-width: 300px;
        }
      }
    }
  }
}

.paper-1 {
  top: 100px;
  @media #{$mq-mini-mobile} {
    top: unset;
  }
}

.square-box-wrapper {
  max-width: 900px;
  margin: auto;

  @media #{$mq-lg} {
    max-width: 1200px;
    overflow-x: auto;
  }
}

.square-box-wrapper::-webkit-scrollbar {
  display: none;
}

.square-box {
  width: 435px;
  padding: 25px;
  margin: 0 10px;
  //width: 100%;
}

.link-box-white {
  border-bottom: 1.5px solid #fffef5;
}

.link-box-black {
  border-bottom: 1.5px solid #181f1c;
}

.link-black:hover {
  color: #181f1c;
  text-decoration: none;
}

.link-white:hover {
  color: #fffef5;
  text-decoration: none;
}

.square-box-1 {
  position: relative;
  right: 25px;
  top: 25px;

  @media #{$mq-lg} {
    position: unset;
  }
}

.square-box-2 {
  position: relative;
  left: 25px;

  @media #{$mq-lg} {
    position: unset;
  }
}

.square-box-3 {
  position: relative;
  top: 25px;
  left: 50px;

  @media #{$mq-lg} {
    position: unset;
  }
}

.money {
  position: relative;
  left: 25px;
  top: 25px;
}

.coin {
  position: relative;
  right: 190px;
  top: 135px;
}

.intro-text {
  position: absolute;
  top: 5px;
  left: 25px;
  width: 450px;
  padding: 10px 5px;

  @media #{$mq-lg} {
    width: 400px;
    color: #181f1c !important;
  }

  @media #{$mq-mini-mobile} {
    // position: unset;

    top: -5px;
    width: 240px;
    left: 15px;
  }
}

.th-box {
  max-width: 450px;
  margin: 0 auto;

  @media #{$mq-mobile} {
  }

  @media #{$mq-mini-mobile} {
    max-width: 280px;
    img {
      width: 280px;
    }
    h2 {
      font-size: 20px;
    }
    p {
      font-size: 14px;
    }
  }
}

.symbol-header {
  max-width: 270px;
  margin: auto;
  padding: 10px 35px;
}

.work-category {
  padding: 10px 0 5px;
  border-bottom: 1px solid #0056a6;
  text-align: center;
  .box {
    border: 1px solid #0056a6;
    padding: 20px;
    width: fit-content;
    margin: auto;

    @media #{$mq-mobile} {
      position: unset;
      padding: 10px;
    }
  }

  hr {
    border-top: 1px solid #0056a6;
  }
}

.boxleft {
  position: relative;
  right: 175px;
}

.boxright {
  position: relative;
  left: 175px;
}

.choose-wrapper {
  background-image: url("~/assets/images/bg_grid_blue.svg");
  position: relative;
  padding-top: 75px;

  @media #{$mq-mini-mobile} {
    padding-top: 30px;
  }

  .header-box {
    border: 1px solid #0056a6;
    padding: 10px;
    width: fit-content;
    margin: auto;

    .content {
      padding: 10px;
    }
  }
  .gradient {
    width: 100%;
    height: 270px;
    background: linear-gradient(
      0deg,
      rgba(0, 86, 166, 0.8) -5.74%,
      rgba(255, 255, 255, 0) 100%
    );
    mix-blend-mode: multiply;
  }
}

.box-1 {
  background-image: url("~/assets/images/box_light.svg");
  width: 457.85px;
  height: 330.08px;
  background-size: cover;
  background-repeat: no-repeat;
  display: flex;
  align-items: flex-end;

  @media #{$mq-mini-mobile} {
    width: 280px;
    height: 201.86px;
  }
}

.box-1:hover,
.box-2:hover {
  background-image: url("~/assets/images/box_hover.svg");

  h4 {
    color: $blue-a !important;
  }
}

.box-2 {
  background-image: url("~/assets/images/folder_dark.svg");
  width: 457.85px;
  height: 330.08px;
  background-size: cover;
  background-repeat: no-repeat;
  display: flex;
  align-items: flex-end;

  @media #{$mq-mini-mobile} {
    width: 280px;
    height: 201.86px;
  }
}

.lottiebox {
  position: absolute;
  bottom: 0;
  z-index: 6;
}

#arrowdown {
  opacity: 0;
  transition: 0.5s;
}

.story-header-box {
  background: #181f1c;

  @media #{$mq-lg} {
    background: #0056a6;
  }
}
</style>
