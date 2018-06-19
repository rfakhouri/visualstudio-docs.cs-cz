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
ms.openlocfilehash: e963472ee51f2439b50807a49425dcd7f6d8443a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791910"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>Zpracování událostí Windows Runtime v jazyce JavaScript
Prostředí Windows Runtime události nenachází v jazyce JavaScript stejným způsobem jako v C++ nebo rozhraní .NET Framework. Nejsou vlastnosti třídy, ale jsou reprezentovány jako řetězec identifikátory, které se budou předávat na třídu `addEventListener` a `removeEventListener` metody. Například můžete přidat obslužné rutiny události pro [Geolocator.PositionChanged](http://msdn.microsoft.com/library/windows/apps/xaml/windows.devices.geolocation.geolocator.positionchanged.aspx) událostí pomocí předání řetězec "positionchanged" `Geolocator.addEventListener` metoda:  
  
```JavaScript  
var locator =  new Windows.Devices.Geolocation.Geolocator();  
locator.addEventListener(  
    "positionchanged",   
     function (ev) {  
        console.log("Got event");  
    });  
```  
  
 Můžete také nastavit `locator.onpositionchanged` vlastnost.  
  
```  
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
 [Pomocí prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)