---
layout: post
title: 'WIFI二维码'
date: 2021-02-04
author: 江小鱼
tags: 工具
---

> 将WPA2加密类型的WIFI名称、密码生成扫描连接的二维码。

<div id="qrcode" style="text-align:center;height:190px;">
    <img src="/assets/img/loading.gif" style="display: block;height:170px;background-color:transparent;">
</div>
<div style="float: right;">
    <input type="checkbox" id="isHidden" /> 是否隐藏网络
</div>
<input type="text" id="name" style="width:100%; border:1px solid rgba(0,0,0,.15);text-align:center;height:77px;margin-top:15px;" maxlength="20" placeholder="输入WIFI名称" />
<input type="password" id="password" style="width:100%; border:1px solid rgba(0,0,0,.15);text-align:center;height:77px;margin-top:15px;" maxlength="32" placeholder="输入WIFI密码" />
<div style="float: right;">
    <a id="download" href="javascript:void(0);">下载二维码</a>
</div>
<script>
    $(function() {
        $('#qrcode').html('');
        var qrcode = qrcode = new QRCode("qrcode", {
            text: "https://imdon.wang",
            width: 170,
            height: 170,
            colorDark : "#000000",
            colorLight : "#ffffff",
            correctLevel : QRCode.CorrectLevel.H
        });
        $('input').keyup(function() {
            make();
        });
        $('#isHidden').change(function() {
            make();
        });
        function make() {
            var codeText = "WIFI:T:WPA2;S:" + $('#name').val() + ";P:" + $('#password').val() + ($('#isHidden').is(":checked") ? ";H:true" : "") + ";;";
            $('#download').attr('href', 'https://qr-generator.qrcode.studio/qr/custom?download=true&file=png&data=' + encodeURIComponent(codeText) + '&size=2000&config=%7B%22body%22%3A%22circle-zebra%22%2C%22eye%22%3A%22frame0%22%2C%22eyeBall%22%3A%22ball0%22%2C%22erf1%22%3A%5B%5D%2C%22erf2%22%3A%5B%5D%2C%22erf3%22%3A%5B%5D%2C%22brf1%22%3A%5B%5D%2C%22brf2%22%3A%5B%5D%2C%22brf3%22%3A%5B%5D%2C%22bodyColor%22%3A%22%23000%22%2C%22bgColor%22%3A%22%23FFFFFF%22%2C%22eye1Color%22%3A%22%23000%22%2C%22eye2Color%22%3A%22%23000%22%2C%22eye3Color%22%3A%22%23000%22%2C%22eyeBall1Color%22%3A%22%23000%22%2C%22eyeBall2Color%22%3A%22%23000%22%2C%22eyeBall3Color%22%3A%22%23000%22%2C%22gradientColor1%22%3Anull%2C%22gradientColor2%22%3Anull%2C%22gradientType%22%3A%22linear%22%2C%22gradientOnEyes%22%3A%22true%22%2C%22logo%22%3A%22https%3A%2F%2Fimdon.wang%2Fassets%2Fimg%2Fwifi_logo.png%22%2C%22logoMode%22%3A%22default%22%7D');
            qrcode.clear();
            qrcode.makeCode(codeText);
        }
    });
</script>
<script type="text/javascript" src="/assets/js/qrcode/qrcode.min.js"></script>
