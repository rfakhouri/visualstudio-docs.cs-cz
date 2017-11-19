---
title: "Zobrazování textu na webových stránkách (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- JavaScript, write
- JavaScript, writing text
ms.assetid: 3c2455e7-2402-45f2-9545-77a2b2490527
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a8c9ea9d0e0300a0d9b71b0b33d7c99c9ac3935c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="displaying-text-in-a-webpage-javascript"></a>Zobrazování textu na webových stránkách (JavaScript)
Existuje několik způsobů, jak zobrazit text na webových stránkách. Každá má své výhody a nevýhody a podporuje konkrétní používá.  
  
## <a name="displaying-text"></a>Zobrazení textu  
  
-   Vytvořte prvek a zapisovat do jeho vlastnost textContent je doporučeným způsobem, jak zobrazit text.  
  
    ```JavaScript  
    <div id="textDiv"></div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        div.textContent = "my text";  
        var text = div.textContent;  
    </script>  
    ```  
  
     V tomto příkladu hodnota `text` je "text". Nicméně, hodnota vyplývající z získání nebo nastavení `textContent` vlastnost na nadřazený uzel může zahrnovat textového obsahu z uzlu, děti. Následující příklad ukazuje, že `textContent` který je nastavená pro podřízený uzel je zahrnuta v hodnotě `textContent` nadřazeného uzlu:  
  
    ```JavaScript  
    <div id="textDiv">  
        <div id="nested"></div>  
    </div>  
    <script type="text/javascript">  
        var div = document.getElementById("textDiv");  
        var nestedDiv = document.getElementById("nested");  
        nestedDiv.textContent = "nested";  
  
        var text = "[" + div.textContent + "]";  
    </script>  
    ```  
  
     V tomto příkladu hodnota `text` je "[nested]".  
  
-   Můžete také vytvořit element a zapisovat do jeho [innerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) nebo [innerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) vlastnosti. Nastavení těchto vlastností ovlivňuje pouze text v elementu samotného, není v jeho podřízených položek. Tyto vlastnosti však mít také některé nevýhody:  
  
    -   [InnerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) vlastnost nefunguje v všechny prohlížeče, takže můžete chtít vyhnout z důvodu kompatibility.  
  
    -   [InnerText](http://msdn.microsoft.com/library/ie/ms533899\(v=vs.85\).aspx) vlastnost je ovlivňován stylů CSS a nezobrazí, pokud je element skrytý.  
  
    -   [InnerHTML](http://msdn.microsoft.com/library/ie/ms533897\(v=vs.85\).aspx) vlastnost získá a nastaví vnořených uzlů a text. Pokud není zabezpečen, se může použít pro vložení skriptu útoky. Kromě toho jeho nastavení na hodnotu text bez značky HTML odebere všechny dříve sada uzlů.  
  
-   Můžete použít `document.write` metoda bez nutnosti vytvářet elementu. Pomocí této metody však způsobí celou webovou stránku vymazat, která nemusí být co chcete použít.  
  
     Následující příklad ukazuje jeden Nevýhody používání `document.write`. Skript slouží k zobrazení času každých 5 sekund, ale zobrazuje čas právě dvakrát. V čase `document.write` je volána při druhém stránce dokončil načítání, a `document.write` pak vymaže celou stránku (zavolá `document.open`). V tomto okamžiku `ShowTime` funkce už existuje.  
  
    ```html  
    <!DOCTYPE html>  
    <html>  
    <head>  
    <script type="text/javascript">  
        function ShowTime()  
        {  
            var dt = new Date();  
            document.write(dt.toTimeString());  
            // var elem = document.getElementById("divElem");  
            // elem.textContent = dt.toTimeString();  
            window.setTimeout("ShowTime();", 5000);  
        }  
    </script>  
    </head>  
  
    <body>  
    <script type="text/javascript">  
        ShowTime();  
    </script>  
    <div id="myDiv"></div>  
    </body>  
    </html>  
  
    ```  
  
     Chcete-li opravit předchozí kód, odeberte řádek kódu, který obsahuje `document.write` a zrušte komentář u dva řádky kódu, které následují označeno jako komentář.  
  
-   Můžete použít také `alert``prompt`, nebo `confirm` funkce, která zobrazuje zprávy v místním okně. Ve většině případů není vhodné používat automaticky otevíraných oken ve webovém prohlížeči. Většina moderních prohlížečů mít nastavení, které automaticky blokovat automaticky otevíraná okna, takže se nemusí zobrazit zprávu. Kromě toho je možné zadat nekonečné smyčce, při použití automaticky otevíraná okna, které znemožňuje, aby uživatele, aby webové stránky obvyklým způsobem.