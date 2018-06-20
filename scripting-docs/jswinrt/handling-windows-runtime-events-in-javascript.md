---
title: Zpracování událostí Windows Runtime v jazyce JavaScript | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1118fa4e6408698187e7f50ca6f9b61bf596a6e
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234943"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>Zpracování událostí Windows Runtime v jazyce JavaScript
Prostředí Windows Runtime události nenachází v jazyce JavaScript stejným způsobem jako v C++ nebo rozhraní .NET Framework. Nejsou vlastnosti třídy, ale jsou reprezentovány jako identifikátory (malého) řetězce, které se budou předávat na třídu `addEventListener` a `removeEventListener` metody. Například můžete přidat obslužné rutiny události pro [Geolocator.PositionChanged](https://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) událostí pomocí předání řetězec "positionchanged" `Geolocator.addEventListener` metoda:  
  
```JavaScript  
var locator = new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 Můžete také nastavit `locator.onpositionchanged` vlastnost:  
  
```JavaScript  
locator.onpositionchanged =    
    function (ev) {  
        console.log("Got event");  
    };  
```  
  
 V jazyce JavaScript argumenty událostí prostředí Windows Runtime jsou vyjádřené objekt jednu událost. V následujícím příkladu metoda obslužné rutiny události `ev` parametr je objekt, který obsahuje odesílatele (vlastnost target) i další argumenty událostí. Argumenty událostí jsou ty, které jsou popsané pro každou jednotlivou událost.  
  
```JavaScript  
function (ev) {  
    console.log("Target: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
  
```  
  
> [!IMPORTANT]
>  Prostředí Windows Runtime funkcí nejsou k dispozici pro aplikace, které běží v aplikaci Internet Explorer.  
  
## <a name="see-also"></a>Viz také  
 [Použití prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)