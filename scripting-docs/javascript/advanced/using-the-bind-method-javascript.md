---
title: Používání metody bind (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bind method [JavaScript]
- this object [JavaScript]
ms.assetid: f608f95b-3b9d-437a-a67a-5a4ef8f6c07f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d185801cc5bba355751147edb79b9c47d21f8eed
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/05/2018
ms.locfileid: "28987864"
---
# <a name="using-the-bind-method-javascript"></a>Používání metody bind (JavaScript)
Jazyk JavaScript `bind` metoda má několik použití. Obvykle se používá k zachování kontextu spuštění pro funkci, která se spouští v jiném kontextu. `bind`Vytvoří novou funkci, která má stejný text jako původní funkce. První argument předaný `bind` Určuje hodnotu `this` – klíčové slovo v svázané funkce. Můžete také předat dalších, volitelných argumentů pro `bind`. Příklady dalších používá, najdete v článku [bind – metoda (Function)](../../javascript/reference/bind-method-function-javascript.md). Příklad použití `bind` částečně funkce, přečtěte si téma [asynchronní programování vzory a tipy v jazyce JavaScript Hilo (pro Windows Store)](http://msdn.microsoft.com/library/windows/apps/jj649740.aspx).  
  
## <a name="preserving-the-execution-context-using-bind"></a>Zachování kontextu spuštění pomocí metody bind  
 `bind` Funkce se často používá při přidávání naslouchacích procesů událostí. V následujícím příkladu kódu `bind` se používá k zachování kontextu aktuálního objektu (`DataObject`). Datový objekt předaný `bind` pomocí `this` – klíčové slovo, které poskytuje přístup k vlastnosti objektu data a funkce při obslužné rutiny události (`dataReadyHandler`) spouští. Pro ilustraci jak `bind` funguje, tento kód vytvoří vlastní události.  
  
```JavaScript  
var data;  
  
var dataReadyEvent = document.createEvent("Event");  
dataReadyEvent.initEvent("dataReady", true, false);  
  
function DataObject() {  
    this.name = "Data Object";  
    this.data = function () {  
        return data;  
    }  
    this.onDataCompleted = dataReadyHandler;  
    document.addEventListener('dataReady', this.onDataCompleted.bind(this));  
    // To see the result of not using bind, comment out the preceding line,   
    // and uncomment the following line of code.  
    // document.addEventListener('dataReady', this.onDataCompleted);  
}  
function dataReadyHandler() {  
    if (console && console.log) {  
        console.log("Data object property value: " + this.name);  
        console.log("Data object property value: " + this.data());  
    }  
}  
  
setTimeout(function () {  
    data = [0, 1, 2, 3];  
    document.dispatchEvent(dataReadyEvent);  
    }, 5000);
  
var dataObj = new DataObject();  
  
// Output:  
// Data Object  
// 0,1,2,3  
  
```  
  
 Pokud můžete Zakomentovat řádek kódu, který používá `bind`, zrušte komentář u řádku kódu, který volá `addEventListener` bez `bind`a poté znovu spusťte kód, `dataReadyHandler` funkce selže. Například v `dataReadyHandler`, `this.name` nedefinované, a `this.data()` způsobí chybu, protože `this` objektu už odkazuje na datový objekt.  
  
## <a name="see-also"></a>Viz také  
 [bind – metoda (Function)](../../javascript/reference/bind-method-function-javascript.md)
