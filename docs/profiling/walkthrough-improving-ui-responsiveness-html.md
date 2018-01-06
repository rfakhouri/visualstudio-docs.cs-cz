---
title: "Návod: Zlepšení odezvy uživatelského rozhraní (HTML) | Microsoft Docs"
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
helpviewer_keywords:
- performance tools, JavaScript [UWP apps]
- performance, JavaScript [UWP apps]
- performance, HTML [UWP apps]
- performance tools, HTML [UWP apps]
ms.assetid: 7e5a2524-dbf5-4a40-b5d6-2d1ed7fff3de
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 2c44751b9a4eb60ddc6124311bd75592777d4cb9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-improving-ui-responsiveness-html"></a>Návod: Zlepšení odezvy uživatelského rozhraní (HTML)
Tento názorný postup vás provede procesem identifikovat a opravit problémy výkonem pomocí [profiler odezvy uživatelského rozhraní HTML](../profiling/html-ui-responsiveness.md). Profileru je k dispozici v sadě Visual Studio pro aplikace UWP pomocí jazyka JavaScript. V tomto scénáři vytvoříte aplikaci test výkonu, která aktualizuje elementů modelu DOM příliš často a používat profileru k identifikaci a řešení tohoto problému.  
  
### <a name="creating-and-running-the-performance-test-app"></a>Vytváření a spouštění výkon testování aplikace  
  
1.  V sadě Visual Studio vytvořte nový projekt Windows Universal jazyka JavaScript. (Vyberte **soubor > Nový > projekt**. Zvolte **JavaScript** v levém podokně a potom zvolte **Windows**, **Windows 10**, pak buď **Universal**, nebo  **Windows Phone**.  
  
2.  > [!IMPORTANT]
    >  Diagnostické výsledky zobrazené v tomto tématu se zobrazují pro aplikace pro Windows 8.  
  
3.  Vyberte jednu z prázdného projektu šablony v prostředním podokně, jako například **prázdnou aplikaci**.  
  
4.  V **název** pole, zadejte název, jako `JS_Perf_Tester`a potom zvolte **OK**.  
  
5.  V **Průzkumníku řešení**, otevřete default.html a vložte následující kód mezi \<textu > značky:  
  
    ```html  
    <div class="wrapper">  
        <button id="content">Waiting for values</button>  
    </div>  
    ```  
  
6.  Otevřete default.css a přidejte následující kód šablon stylů CSS:  
  
    ```css  
    #content {  
        margin-left: 100px;  
        margin-top: 100px;  
    }  
    ```  
  
7.  Otevřete default.js a nahraďte všechny kód s tímto kódem:  
  
    ```javascript  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var activation = Windows.ApplicationModel.Activation;  
  
        var content;  
        var wrapper;  
  
        app.onactivated = function (args) {  
            if (args.detail.kind === activation.ActivationKind.launch) {  
                if (args.detail.previousExecutionState !== activation.ApplicationExecutionState.terminated) {  
  
                    content = document.getElementById("content");  
                    wrapper = document.querySelector(".wrapper");  
  
                    content.addEventListener("click", handler);  
  
                } else {  
                }  
  
                args.setPromise(WinJS.UI.processAll());  
            }  
        };  
  
        app.oncheckpoint = function (args) {  
        };  
  
        app.start();  
  
        var idx = 0;  
        var count = 0;  
        var max = 5000;  
        var text = ["what", "is", "the", "Matrix?"];  
        var color = ["red", "crimson", "maroon", "purple"];  
  
        function increment() {  
  
            setTimeout(function () {  
  
                idx++;  
                count++;  
  
                if (idx > 3) { idx = 0; }  
                if (count < max) { increment(); }  
  
            }, 1000);  
        }  
  
        function setValues() {  
  
            content = document.getElementById("content");  
            content.removeNode(true);  
  
            var newNode = document.createElement("button");  
            newNode.id = "content";  
            newNode.textContent = text[idx];  
            //newNode.textContent = getData();  
            newNode.style.backgroundColor = color[idx];  
            //newNode.style.animationName = "move";  
            //count++;  
  
            wrapper.appendChild(newNode);  
  
        }  
  
        function update() {  
  
            setTimeout(function () {  
  
                setValues();  
                if (count < max) { update(); }  
            });  
        }  
  
        function handler(args) {  
  
            content.textContent = "eenie";  
            increment();  
            update();  
        }  
  
    })();  
  
    ```  
  
8.  Zvolte klávesy F5 spusťte ladění. Ověřte, zda **čekání hodnoty** na stránce se zobrazí tlačítko.  
  
9. Zvolte **čekání hodnoty** a ověřte, že text tlačítka a barvu aktualizovat přibližně jednou za sekundu. Toto je záměrné.  
  
10. Přepněte zpět na Visual Studio (Alt + Tab) a poté zvolte Shift + F5 ukončete ladění.  
  
     Teď, když ověříte, že aplikace funguje, můžete zkontrolovat jeho výkon pomocí profileru.  
  
### <a name="analyzing-performance-data"></a>Analýza dat výkonu  
  
1.  Na **ladění** panelu nástrojů v **spustit ladění** seznam, vyberte jednu z emulátorů Windows Phone nebo **simulátoru**.  
  
2.  Na **ladění** nabídky, zvolte **výkonu a Diagnostika**.  
  
3.  V **nástroje**, zvolte **odezvy uživatelského rozhraní HTML**a potom zvolte **spustit**.  
  
     V tomto kurzu budete mít připojení profileru k spouštěný projekt. Informace o dalších možnostech, jako je připojení profileru k aplikaci nainstalovanou v tématu [odezvy uživatelského rozhraní HTML](../profiling/html-ui-responsiveness.md).  
  
     Když spustíte profileru, může se zobrazit řízení uživatelských účtů, vyžaduje vaše oprávnění ke spuštění VsEtwCollector.exe. Zvolte **Ano**.  
  
4.  Ve spuštěné aplikaci, vyberte **čekání hodnoty** a počkejte asi 10 sekund. Ověřte, že text tlačítka a barvu aktualizovat přibližně jednou za sekundu.  
  
5.  Z spuštěné aplikaci přepněte do sady Visual Studio (Alt + Tab).  
  
6.  Zvolte **zastavit shromažďování**.  
  
     Profileru zobrazí informace na nové záložce v sadě Visual Studio. Když se podíváte na využití procesoru a dat visual propustnosti (FPS), můžete snadno identifikovat trendy několik:  
  
    -   Zvyšuje zatížení procesoru výrazně po o 3 sekund (při stisknutí tlačítka **čekání hodnoty** tlačítko) a na zobrazuje zrušte vzor událostí (konzistentní směs skriptování, stylu a vykreslování události) z tohoto bodu.  
  
    -   Visual propustnost není ovlivněná a FPS zůstává na 60 v rámci (to znamená, nejsou žádné vynechaných rámce).  
  
     Podívejme se na typické oddíl graf využití procesoru a zjistěte, co je to aplikace v tomto období vysoké aktivity.  
  
7.  Vyberte jednu až dvě druhou část uprostřed graf využití procesoru (buď kliknutím a přetažením nebo použijte kartu a šipku klíče). Následující obrázek znázorňuje graf využití procesoru po provedení výběru. Oblasti nesdílené je výběr.  
  
     ![Graf využití procesoru](../profiling/media/js_htmlviz_app_cpu.png "JS_HTMLViz_App_CPU")  
  
8.  Zvolte **přiblížit**.  
  
     Změn grafu zobrazíte vybrané období podrobněji. Následující obrázek znázorňuje graf využití procesoru po přiblížení. (Konkrétní data se mohou lišit, ale bude obecné vzor zřejmá.)  
  
     ![V zobrazení možnosti](../profiling/media/js_htmlviz_app_zoom.png "JS_HTMLViz_App_Zoom")  
  
     Časová osa podrobnosti v dolním podokně ukazuje příklad podrobnosti pro vybrané období.  
  
     ![Časová osa podrobnosti](../profiling/media/js_htmlviz_app_details.png "JS_HTMLViz_App_Details")  
  
     Události v podrobnostech časová osa potvrďte viditelné trendy v graf využití procesoru: existuje mnoho událostí probíhající přes krátkodobě. Časová osa zobrazení podrobností uvádí, že tyto události jsou `Timer`, `Layout`, a `Paint` události.  
  
9. Pomocí místní nabídky (nebo klikněte pravým tlačítkem myši) mezi `Timer` události v dolním podokně a zvolte **filtr událostí**. Následující obrázek znázorňuje příklad podrobnosti typické pro jednu z `Timer` události v této testovací aplikace.  
  
     ![Událost časovače](../profiling/media/js_htmlviz_app_timer.png "JS_HTMLViz_App_Timer")  
  
     Celou řadu fakty může shromažďovat informace z dat. Příklad:  
  
    -   Každý `Timer` událostí, barevné kódování identifikovat jako skriptovací událost, obsahuje volání `document.createElement`, za nímž následují styl výpočet a volání `style.backgroundColor` a `appendChild()`.  
  
    -   V krátkém časovém úseku, v vybrané (přibližně jednu až dvě sekundy), existuje velký počet `Timer`, `Layout`, a `Paint` probíhající události. `Timer` Daleko častěji než jedna aktualizace za sekundu, které je viditelně zřejmá po spuštění aplikace a zvolte dojde k událostem **čekání hodnoty** tlačítko.  
  
10. Chcete-li prozkoumat, zvolte odkaz na anonymní funkce pro jednu ze `Timer` události ve spodní levé části podokna. Otevře se v souboru default.js následující funkce:  
  
    ```javascript  
    function update() {  
  
        setTimeout(function () {  
  
            setValues();  
            if (count < max) { update(); }  
        });  
    }  
    ```  
  
     Tato funkce rekurzivní nastaví smyčku, která volá `setValues()` funkci, která aktualizuje tlačítko v uživatelském rozhraní. Porovnáním různých časovače událostí v profileru zjistili jste, že většina nebo všechny události časovače výsledkem tento kód, který se spouští příliš často, zobrazí se pravděpodobně zde vznikl problém.  
  
### <a name="fixing-the-performance-issue"></a>Opravit problémy s výkonem  
  
1.  Nahraďte `update()` funkce následujícím kódem:  
  
    ```javascript  
    function update() {  
  
        setTimeout(function () {  
  
            setValues();  
            if (count < max) { update(); }  
        }, 1000 );  
    }  
    ```  
  
     Tuto pevnou verzi kód obsahuje 1000 milisekund zpoždění, které byl tento parametr vynechán z předchozí verze kódu, což vede k použití výchozí hodnoty. Z dat profileru, zdá se, že výchozí hodnota je nulový počet milisekund, které způsobily `setValues()` funkce spuštění příliš často.  
  
2.  Znovu spusťte profiler odezvy uživatelského rozhraní HTML a zkontrolujte graf využití procesoru. Zjistíte, že nadměrné události jsou pryč a využití procesoru klesla k téměř nulové. Napravila.  
  
## <a name="see-also"></a>Viz také  
 [Rychlost odezvy HTML UI](../profiling/html-ui-responsiveness.md)