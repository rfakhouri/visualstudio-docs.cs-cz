---
title: "Správa naslouchacích procesů událostí | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 87717f5d-b0c6-4c8d-a293-476002b7bfcf
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6a97c579716b9964b8dfb93db419e9a70160d33a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="managing-event-listeners"></a>Správa naslouchacích procesů událostí
Pokud doba platnosti elementu DOM nebo objektu se liší od životnost jeho naslouchací proces související události, možná budete muset použít [removeEventListener](http://msdn.microsoft.com/library/ie/ff975250\(v=vs.85\).aspx)nevracení metoda zrušení paměti.  
  
## <a name="event-listeners-and-object-scope"></a>Naslouchacích procesů událostí a obor objektu  
 Následující příklad kódu ukazuje kód, který může mít za následek paměťově úniku, kdy `dataObjFactory()` funkce je volána. V tomto kódu je zaregistrován naslouchací proces událostí pro objekt dat pokaždé, když je vytvořen nový objekt data. Chcete-li k dispozici v aktuální datový objekt `dataReady()` obslužné rutiny události, [bind – metoda (Function)](../../javascript/reference/bind-method-function-javascript.md) se používá v `addEventListener`.  
  
```JavaScript  
 var data;  
 var dataObj;  
  
 var dataReadyEvent = document.createEvent("Event");  
 dataReadyEvent.initEvent("dataReady", true, false);  
  
 function DataObject() {  
  
     this.name = "Data Object";  
     this.data = function () {  
         return data;  
     }  
     this.onDataCompleted = dataReady;  
     // this.handlerRef = this.onDataCompleted.bind(this);  
  
     // document.addEventListener('dataReady', this.handlerRef);  
     document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
 }  
  
 // Runs when the data is available.  
 function dataReady() {  
     if (console && console.log) {  
         console.log("object value: " + this.name);  
         console.log("object value: " + this.data());  
     }  
 }  
  
setTimeout(function () {  
    // Generate data after a timeout period.  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
}, 10000);  
  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             // The following line of code has no effect.  
             document.removeEventListener('dataReady', dataObj.onDataCompleted);  
             dataObj = null;  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
 dataObjFactory();  
```  
  
 Naslouchací proces pro každý datový objekt není zaregistrována `document` objekt, který má jinou dobu života než datových objektů. Naslouchací proces registrovaných událostí pro každý datový objekt zabrání se shromážděných stejně dlouho jako uvolňování paměti `document` objekt zůstane v oboru. (V některé moderní vzory návrhu JavaScript, objekt dokument zůstane v oboru po dobu jeho existence webové aplikace.) Aby se zabránilo nevrácenou pamětí `removeEventListener` je volána `dataObjFactory` funkce. Tento kód však selže, protože `removeEventListener` nebyla zavolána na vázané verzi obslužné rutiny události, který je vrácen `bind`funkce.  
  
 Tento kód, a zpřístupnit datových objektů pro uvolňování paměti, musíte nejprve uložit odkaz na vázané verzi obslužné rutiny události, jak je znázorněno v následujícím kódu a poté předat uložené odkaz `addEventListener`. Zde je kód opravené pro `DataObject`:  
  
```JavaScript  
function DataObject() {  
  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReady;  
    this.handlerRef = this.onDataCompleted.bind(this);  
  
    document.addEventListener('dataReady', this.handlerRef);  
    // document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
}  
  
```  
  
 Nakonec je třeba volat `removeEventListener` na odkaz na uložené (`handlerRef`) vázané funkce. Zde je kód opravené pro `dataObjFactory`:  
  
```JavaScript  
function dataObjFactory() {  
     for (var x = 0; x < 100; x++) {  
         if (dataObj) {  
             document.removeEventListener('dataReady', dataObj.handlerRef);  
         }  
         dataObj = new DataObject();  
     }  
 }  
  
```  
  
 Nyní volání `removeEventListener` funguje a nepotřebné datové objekty, které může být shromážděných i při uvolňování paměti `document` objekt zůstane v oboru.