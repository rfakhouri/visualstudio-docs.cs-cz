---
title: Ladění kódu HTML a CSS ukázka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 51893967-98c8-4141-ba40-03646f221760
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2636e2a3a6fe3e99213198eb3296a765a664b4f4
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227090"
---
# <a name="debug-html-and-css-sample-code"></a>Ladění ukázkového kódu HTML a CSS

Kód v tomto tématu se ukázkový soubor pro [rychlý start: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md). Chyby podle návrhu k dispozici v tomto rychlém startu jsou opravené v této verzi kódu.

## <a name="sample-code"></a>Vzorový kód
Následující kód HTML je používán \<text > značky v tomto rychlém startu.

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

Následující šablony stylů CSS ukazuje přidání provedené default.css.

```css
#fView {
    background-color:#0094ff;
    height: 500px;
    margin: 25px;
}
```

Následující příklad kódu ukazuje kompletní kód jazyka JavaScript v souboru default.js. Odkazy na obory názvů WinJS pro tento kód se v souboru default.html šablony.

```javascript
(function () {
    "use strict";

    var app = WinJS.Application;
    var activation = Windows.ApplicationModel.Activation;

    var myData = [];
    for (var x = 0; x < 3; x++) {
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

        pages.setAt(0, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg" });
        pages.setAt(1, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg" });
        pages.setAt(2, { flipImg: "http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg" });
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
[Rychlý start: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)
