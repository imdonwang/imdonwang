---
layout: post
title: '新年快乐'
date: 2021-02-12
author: 江小鱼
tags: 春节
---

>祝新年快乐，牛年大吉，万事顺意。[烟花][爆竹][福][庆祝][爱心]

<div style="width:100%;text-align:center;">
    <img id="happy" src="/assets/img/cny_2021/jpg/fc8fd5.jpeg" alt="新年快乐" height="128" />
</div>
<script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.3.3/dist/confetti.browser.min.js"></script>
<script>
    var gifs = ['zany_face', 'partying_face', 'love_you_gesture', 'party_popper', 'fire', 'fireworks', 'woman_juggling', 'bottle_with_popping_cork', 'clinking_beer_mugs', 'drum', 'ferris_wheel', 'fishing_pole', 'slot_machine', 'rocket', 'growing_heart'];
    $(function() {
        $('body').removeClass('night-mode');
        var i = 0;
        setInterval(function() {
            $('#happy').hide();
            if(i < gifs.length) {
                $('#happy').attr('src', '/assets/img/cny_2021/gif/' + gifs[i] + '.gif');
            } else {
                $('#happy').attr('src', '/assets/img/cny_2021/jpg/fc8fd5.jpeg');
                i = 0;
            }
            $('#happy').show();
            i++;
        }, 2000);
    });
    var duration = 5 * 1000;
    var animationEnd = Date.now() + duration;
    var defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 0 };
    function randomInRange(min, max) {
        return Math.random() * (max - min) + min;
    }
    var interval = setInterval(function() {
        var timeLeft = animationEnd - Date.now();
        if (timeLeft <= 0) {
            return clearInterval(interval);
        }
        var particleCount = 50 * (timeLeft / duration);
        confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.1, 0.3), y: Math.random() - 0.2 } }));
        confetti(Object.assign({}, defaults, { particleCount, origin: { x: randomInRange(0.7, 0.9), y: Math.random() - 0.2 } }));
    }, 250);
</script>