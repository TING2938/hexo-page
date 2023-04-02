---
title: JHL, I Love You
date: 5200-13-14 21:00:00
tags: Love
categories: Love
excerpt:  YT 😘 JHL
---

<label>YT 😘 JHL</label>
<label id="div1"></label>

<script>
    function time() {
        var date1 = new Date('2020/12/30 21:0:0');    //开始时间
        var date2 = new Date();
        var date3 = date2.getTime() - date1.getTime(); //时间差秒

        //计算出相差天数
        var days = Math.floor(date3 / (24 * 3600 * 1000));
        //计算出小时数
        var leave1 = date3 % (24 * 3600 * 1000);  //计算天数后剩余的毫秒数
        var hours = Math.floor(leave1 / (3600 * 1000));
        //计算相差分钟数
        var leave2 = leave1 % (3600 * 1000);       //计算小时数后剩余的毫秒数
        var minutes = Math.floor(leave2 / (60 * 1000));
        //计算相差秒数
        var leave3 = leave2 % (60 * 1000);     //计算分钟数后剩余的毫秒数
        var seconds = Math.round(leave3 / 1000);
        var str = "我们相爱了 " + days + "天" + hours + "时" + minutes + "分" + seconds + "秒";
        var div1 = document.getElementById("div1");
        div1.innerHTML = str;
    }
    setInterval(time, 1000);
</script>

