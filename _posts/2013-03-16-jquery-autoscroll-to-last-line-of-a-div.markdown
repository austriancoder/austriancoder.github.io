---
layout: post
title: 'JQuery: autoscroll to last line of a div'
date: '2013-03-16 17:18:58'
tags:
- jquery
---


Image you are working on a small web application where you use a JQuery UI dialog
 to inform the user about the current process.

 <ul id="progress" style="width: 300px; height: 200px; overflow: auto"> </ul>

Triggered via SSE I am appending some messages via JavaScript.

 $('#progress').append("<span class='ui-icon ui-icon-alert' style='float: left; margin-right: .3em';></span>" + stderr + "<br>");

In order to automaticly scroll to the last line I am using this two magic lines of JavaScript:

 var height = $('#progress')[0].scrollHeight; $('#progress').scrollTop(height);

It is simple as that.
