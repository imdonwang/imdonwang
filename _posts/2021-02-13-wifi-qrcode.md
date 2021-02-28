---
layout: post
title: 'WIFI二维码'
date: 2021-02-28
author: 江小鱼
tags: 安全
---

> 将WIFI名称、密码生成扫描连接的二维码。

<div id="qrcode" style="text-align:center;height:190px;">
    <img src="/assets/img/loading.gif" style="display: block;height:170px;background-color:transparent;">
</div>
<input type="text" id="name" style="width:100%; border:1px solid rgba(0,0,0,.15);text-align:center;height:77px;margin-top:15px;" maxlength="20" placeholder="输入WIFI名称" />
<input type="password" id="password" style="width:100%; border:1px solid rgba(0,0,0,.15);text-align:center;height:77px;margin-top:15px;" maxlength="32" placeholder="输入WIFI密码" />
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
            var codeText = "WIFI:T:WPA2;S:" + $('#name').val() + ";P:" + $('#password').val() + ";;";
            qrcode.clear();
            qrcode.makeCode(codeText);
        });
    });
</script>
<script type="text/javascript" src="/assets/js/qrcode/qrcode.min.js"></script>
