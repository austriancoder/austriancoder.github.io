---
layout: post
title: Configure git send-email for gmail
date: '2015-04-06 20:53:34'
tags:
- email
- git
---


Today I did a fresh installation of Fedora on my Chromebook and need to setup git send-email. Usually I need to do this step once every 1-2 years I thought it might be a good idea to write it down.

Edit ~/.gitconfig

 [sendemail] from = Firstname Lastname <email@gmail.com> smtpserver = smtp.gmail.com smtpuser = email@gmail.com smtpencryption = tls smtppass = PASSWORD chainreplyto = false smtpserverport = 587

As I am using Googles two factor authentication I needed to generate an app specific password.
