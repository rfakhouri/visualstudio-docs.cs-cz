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
ms.openlocfilehash: f7e5780a2462e8980c22c474ae6236c87aee599b
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36302805"
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
  
Další rozdíl mezi .NET/C++ a JavaScript je počet parametrů provedenou obslužné rutiny události. V rozhraní .NET/C++, obslužná rutina přebírá dva: odesílatel události a data události. V jazyce JavaScript, jsou dva seskupeny jako jeden `Event` objektu. V následujícím příkladu `ev` parametr obsahuje odesílatel události ( `target` vlastnosti) a vlastnosti dat událostí (zde právě `position`). Vlastnosti data události jsou ty, které jsou popsané pro každou jednotlivou událost.
  
```JavaScript  
function (ev) {  
    console.log("Sender: " + ev.target);  
    console.log("Position: " +  
        ev.position.latitude + "," +  
        ev.position.longitude);  
};  
```  
  
> [!IMPORTANT]
>  Prostředí Windows Runtime funkcí nejsou k dispozici pro aplikace, které běží v aplikaci Internet Explorer.  
  
## <a name="see-also"></a>Viz také  
 [Použití prostředí Windows Runtime v jazyce JavaScript](../jswinrt/using-the-windows-runtime-in-javascript.md)
