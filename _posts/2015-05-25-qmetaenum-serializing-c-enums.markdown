---
layout: post
title: 'QMetaEnum: Serializing C++ Enums'
date: '2015-05-25 19:42:28'
tags:
- enum
- c
- qt5
- serializing
---


I think that almost every C++ programmer looked into a nice and easy way to do C++ Enum serialization. You may want to store the Enum value in a human readable format (json, ini, ..) and later you may also want to read back the value into the object.

You have here two way how to archive your goal. Use simple int values to represent the Enum value or use Strings. The big advantage with strings it that you do not have to lookup what the meaning of value 4 is, but you can name the value with a String.

Here I will present you with an non QObject based way of doing it in Qt5. You may wonder why I do not want to use a QObject as base for my class. The answer is quite simple. I need to be able to have a copy constructor and assignment operator for my class.

So lets start with the simple class Item which has Enum called Type in it.

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33.js?file=item.h"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33).</noscript></div>The big goal is to get Item::type() and Item::setType(QString) working as expected. Here is a small demo main(), which will be used for testing.

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33.js?file=main.cpp"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33).</noscript></div>We exspect the following output:

“APPLE”
 “CAR”
 “BIRD”

Here Qt’s MetaObject system comes to help. We use the MetaObject to get the correct QMetaEnum and make use of its valueToKey(..) and keyToValue(..) methods.

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33.js?file=item.cpp"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33).</noscript></div>In order to get this up and working we need to modify our header file.

<div class="oembed-gist"><script src="https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33.js?file=item_2.h"></script><noscript>View the code on [Gist](https://gist.github.com/austriancoder/9bb0c0782aafa4bb1dbcc653e9442a33).</noscript></div>The needed pars are here

- Q_GADGET to get the processed by the meta object compiler (moc)
- Q_ENUMS to ‘export’ the enum to the metaObject

Qt’s MetaObject system saved my day and helped me to easily serialize C++ Enums in a very elegant way. The other more hacky solution would have been a big if-castle to check for each possible value and do everything on my own. But this could lead to problems if the Enum gets extended by an other developer not aware of the hand-written conversion methods.

All in all I am very happy with this solution.
