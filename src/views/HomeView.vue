<template>
  <button @click="handleClick">take pic</button>
  <div id="capture" class="bg-white shadow-custom" style="direction: rtl">
    <div class="grid grid-cols-12 h-[950px]">
      <div class="col-span-4 border-l-4 border-gray-300">
        <div>
          <img src="https://placehold.co/300x600" />
        </div>
        <div class="pt-[70px] px-10">
          <div>
            <div class="text-2xl font-bold mb-3">ویژگی های فردی</div>
            <ul class="text-gray-500">
              <li class="font-bold my-2">ایپسوم متن ساختگی با تولید</li>
              <li class="font-bold my-2">ایپسوم متن ساختگی با تولید</li>
            </ul>
          </div>
          <div class="mt-10">
            <div class="text-2xl font-bold mb-3">تحصیلات</div>
            <ul class="text-gray-500">
              <li class="font-bold my-2">ایپسوم متن ساختگی با تولید</li>
              <li class="font-bold my-2">ایپسوم متن ساختگی با تولید</li>
            </ul>
          </div>
        </div>
      </div>
      <div class="col-span-8">
        <div class="pt-[110px] px-10">
          <div>
            <div class="text-4xl font-bold">محمد امین منتظری</div>
            <div class="text-base font-bold text-gray-500 mt-1" style="letter-spacing: 2px">
              کارشناس مدیریت امور بانکی
            </div>
          </div>
          <div class="h-[30px]" />
          <div>
            <div class="text-2xl font-bold mb-2">هدف</div>
            <div class="text-base text-gray-600 font-semibold">
              لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ، و با استفاده از طراحان
              گرافیک است، چاپگرها و متون بلکه روزنامه و مجله در ستون و سطرآنچنان که لازم است،
            </div>
          </div>
          <div class="h-[30px]" />
          <div>
            <div class="text-2xl font-bold mb-2">سابقه کاری</div>
            <div>
              <div class="text-base text-gray-600 font-semibold">
                ورم ایپسوم با تولید سادگی نامفهوم
              </div>
              <ul class="list-disc my-4 ms-5 font-medium text-base">
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
              </ul>
            </div>
            <div>
              <div class="text-base text-gray-600 font-semibold">
                ورم ایپسوم با تولید سادگی نامفهوم
              </div>
              <ul class="list-disc my-4 ms-5 font-medium text-base">
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
                <li>ورم ایپسوم با تولید سادگی نامفهو</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
import * as htmlToImage from 'html-to-image';
import html2canvas from 'html2canvas'
import { jsPDF } from "jspdf";
const handleClick = ()=>{
  var node = document.getElementById('capture');
  htmlToImage.toPng(node)
  .then(function (dataUrl) {
    var img = new Image();
    img.src = dataUrl;
    document.body.appendChild(img);
  })
  .catch(function (error) {
    console.error('oops, something went wrong!', error);
  });
  
    // html2canvas(document.querySelector("#capture")).then(canvas => {
    //   document.body.appendChild(canvas)

    //   var imgData = canvas.toDataURL("image/jpeg", 1.0);
    //   var pdf = new jsPDF();

    //   pdf.addImage(imgData, 'JPEG', 0, 0);
    //   pdf.save("download.pdf");
    // });
}
</script>
<style>
.shadow-custom {
  box-shadow: rgba(17, 12, 46, 0.15) 0px 48px 100px 0px;
}
</style>
