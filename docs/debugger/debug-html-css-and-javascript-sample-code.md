---
title: "Ladění ukázkový kód HTML, CSS a JavaScript | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 51893967-98c8-4141-ba40-03646f221760
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 762caca321cdda941fd295306fdfdf73e03b0aae
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debug-html-css-and-javascript-sample-code"></a>Ladění ukázkový kód HTML, CSS a JavaScript
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Kód v tomto tématu je ukázkový soubor pro [rychlý úvod: ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md). V této verzi kódu jsou opravit chyby, které jsou záměrné součástí rychlý start.  
  
## <a name="sample-code"></a>Ukázkový kód  
 Následující kód HTML se používá v \<textu > značku rychlý start.  
  
```html  
<div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
         style="display:none">  
    <div class="fixedItem" >  
        <img src="#" data-win-bind="src: flipImg" />  
    </div>  
</div>  
<div id="fView" data-win-control="WinJS.UI.FlipView" data-win-options="{  
    itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
</div>  
```  
  
 Následující CSS ukazuje dodatky provedené default.css.  
  
```css  
#fView {  
    background-color:#0094ff;  
    height: 500px;  
    margin: 25px;  
}  
```  
  
 Následující příklad kódu ukazuje kompletní kód jazyka JavaScript v souboru default.js. Odkazy na obory názvů WinJS pro tento kód je v souboru default.html šablony.  
  
```javascript  
(function () {  
    "use strict";  
  
    var app = WinJS.Application;  
    var activation = Windows.ApplicationModel.Activation;  
  
    var myData = [];  
    for (var x = 0; x < 4; x++) {  
        myData[x] = { flipImg: "/images/logo.png" }  
    };  
  
    var pages = new WinJS.Binding.List(myData, { proxy: true });  
  
    app.onactivated = function (args) {  
        if (args.detail.kind === activation.ActivationKind.launch) {  
            if (args.detail.previousExecutionState !==  
            activation.ApplicationExecutionState.terminated) {  
                // TODO: . . .  
            } else {  
                // TODO: . . .  
            }  
            args.setPromise(WinJS.UI.processAll());  
  
            updateImages();  
        }  
    };  
  
    function updateImages() {  
  
        pages.setAt(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
        pages.setAt(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
        pages.setAt(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
    };  
  
    app.oncheckpoint = function (args) {  
    };  
  
    app.start();  
  
    var publicMembers = {  
        items: pages  
    };  
  
    WinJS.Namespace.define("Data", publicMembers);  
  
})();  
```  
  
## <a name="see-also"></a>Viz také  
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)