---
title: "Návod: Vyhledání nevrácené paměti (JavaScript) | Microsoft Docs"
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
helpviewer_keywords: memory leaks, JavaScript example
ms.assetid: f595412f-776b-49a2-8433-ea0062c6904d
caps.latest.revision: "31"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 13d9fd328ffab5c182078e46bbd832cddcba6fd9
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-find-a-memory-leak-javascript"></a>Návod: Vyhledání nevrácené paměti (JavaScript)
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Tento názorný postup vás provede procesem identifikovat a opravit problém jednoduché paměti pomocí analyzátor paměti jazyka JavaScript. Analyzátor paměti jazyka JavaScript je k dispozici v sadě Visual Studio pro aplikace UWP vytvořená pro systém Windows pomocí jazyka JavaScript. V tomto scénáři vytvoříte aplikaci, která nesprávně uchovává DOM elementů v paměti místo uvolnění elementů stejnou rychlostí, ve které byly vytvořeny.  
  
 Sice velmi konkrétní důvod nevrácená paměť systému v této aplikaci, tady uvedené kroky ukazují pracovní postup, který je obvykle efektivní izolovat objekty, které jsou vracena paměť.  
  
### <a name="running-the-javascript-memory-analyzer-test-app"></a>Spuštění aplikace testovací analyzátor paměti jazyka JavaScript  
  
1.  V sadě Visual Studio, vyberte **soubor**, **nový**, **projektu**.  
  
2.  Zvolte **JavaScript** v levém podokně a potom zvolte **Windows**, **Windows 8**, pak buď **Universal** nebo  **Windows Phone aplikace**.  
  
    > [!IMPORTANT]
    >  Využití paměti výsledky zobrazeny v tomto tématu jsou porovnávaný aplikace pro Windows 8.  
  
3.  Vyberte **prázdnou aplikaci** šablona projektu v prostředním podokně.  
  
4.  V **název** pole, zadejte název, jako `JS_Mem_Tester`a potom zvolte **OK**.  
  
5.  V **Průzkumníku řešení**, otevřete default.html a vložte následující kód mezi \<textu > značky:  
  
    ```html  
    <div class="wrapper">  
        <div id="item"></div>  
        <button class="memleak" style="display: block" >Leak Memory</button>  
    </div>  
    ```  
  
    > [!IMPORTANT]
    >  Pokud používáte šablonu pro univerzální aplikace pro Windows 8.1, je potřeba aktualizovat kód HTML a CSS v obou. Windows a. WindowsPhone projekty.  
  
6.  Otevřete default.css a přidejte následující kód šablon stylů CSS:  
  
    ```css  
    .memleak {  
        position: absolute; top: 100px; left: 100px;  
    }  
    ```  
  
7.  Otevřete default.js a nahraďte všechny kód s tímto kódem:  
  
    ```javascript  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var activation = Windows.ApplicationModel.Activation;  
  
        var wrapper;  
        var elem;  
  
        app.onactivated = function (args) {  
            if (args.detail.kind === activation.ActivationKind.launch) {  
                if (args.detail.previousExecutionState !== activation.ApplicationExecutionState.terminated) {  
                } else {  
                }  
                args.setPromise(WinJS.UI.processAll());  
  
                elem = document.getElementById("item");  
                wrapper = document.querySelector(".wrapper");  
                var btn = document.querySelector(".memleak");  
                btn.addEventListener("click", btnHandler);  
                run();  
            }  
        };  
  
        app.oncheckpoint = function (args) {  
        };  
  
        app.start();  
  
        function run() {  
            initialize();  
            load();  
        }  
  
        function initialize() {  
  
            if (wrapper != null) {  
                elem.removeNode(true);  
            }  
        }  
  
        function load() {  
  
            var newDiv = document.createElement("div");  
  
            newDiv.style.zIndex = "-1";  
            newDiv.id = "item";  
  
            wrapper.appendChild(newDiv);  
        }  
  
        function btnHandler(args) {  
            run();  
        }  
  
    })();  
    ```  
  
8.  Zvolte klávesy F5 spusťte ladění. Ověřte, zda **nevracení paměti** na stránce se zobrazí tlačítko.  
  
9. Přepněte zpět na Visual Studio (Alt + Tab) a poté zvolte Shift + F5 ukončete ladění.  
  
     Teď, když ověříte, že aplikace funguje, můžete zkontrolovat využití paměti.  
  
### <a name="analyzing-the-memory-usage"></a>Analýza využití paměti  
  
1.  Na **ladění** panelu nástrojů v **spustit ladění** vyberte cíl ladění pro aktualizovaný projekt: buď jedné emulátorů Windows Phone nebo **simulátoru**.  
  
    > [!TIP]
    >  Pro aplikace pro UPW, můžete také zvolit **místního počítače** nebo **vzdáleného počítače** v tomto seznamu. 
  
2.  Na **ladění** nabídce zvolte **profileru výkonu...** .  
  
3.  V **nástroje**, zvolte **paměť jazyka JavaScript**a potom zvolte **spustit**.  
  
     V tomto kurzu budete mít připojuje analyzátor paměti k spouštěný projekt. Informace o dalších možnostech, jako je analyzátor paměti se připojuje k nainstalovanou aplikaci, najdete v části [paměť jazyka JavaScript](../profiling/javascript-memory.md).  
  
     Když spustíte analyzátor paměti, může se zobrazit řízení uživatelských účtů, vyžaduje vaše oprávnění ke spuštění VsEtwCollector.exe. Zvolte **Ano**.  
  
4.  Vyberte **nevracení paměti** tlačítko čtyřikrát za sebou.  
  
     Když zvolíte tlačítko, událostí zpracování kódu v pracovních nemá default.js, který bude mít za následek únik paměti. Toto budete používat k diagnostickým účelům.  
  
    > [!TIP]
    >  Opakující se scénář, který chcete testovat nevrácená paměť systému usnadňuje vyfiltrovat nezajímavá informace, například objekty, které jsou přidány do halda během inicializace aplikace nebo při načítání stránky.  
  
5.  Z spuštěné aplikaci přepněte do sady Visual Studio (Alt + Tab).  
  
     Analyzátor paměti jazyka JavaScript zobrazí informace na nové záložce v sadě Visual Studio.  
  
     Graf paměti tato zobrazení se souhrnnými informacemi ukazuje proces využití paměti v průběhu času. Zobrazení také poskytuje příkazy jako **proveďte haldy snímku**. Snímek poskytuje podrobné informace o využití paměti v určitém čase. Další informace najdete v tématu [paměť jazyka JavaScript](../profiling/javascript-memory.md).  
  
6.  Zvolte **proveďte haldy snímku**.  
  
7.  Přepněte do aplikace a zvolte **nevracení paměti**.  
  
8.  Přepněte do sady Visual Studio a zvolte **proveďte haldy snímku** znovu.  
  
     Tento obrázek ukazuje snímek směrného plánu (#1) a snímků č. 2.  
  
     ![Směrný plán snímku a snímek 2](../profiling/media/js_mem_app_snapshot2.png "JS_Mem_App_Snapshot2")  
  
    > [!NOTE]
    >  Emulátor Windows Phone nezobrazuje snímek obrazovky aplikace v době pořízení snímku.  
  
9. Přepněte do aplikace a zvolte **nevracení paměti** tlačítko znovu.  
  
10. Přepněte do sady Visual Studio a zvolte **proveďte haldy snímku** třetí dobu.  
  
    > [!TIP]
    >  Pomocí třetí snímku v tomto pracovním postupu, můžete filtrovat mění ze snímku standardních hodnot na druhý snímek které nejsou přidruženy k nevracení paměti. Například může být očekávané změny jako aktualizace záhlaví a zápatí na stránce, která způsobí vygenerování některé změny využití paměti, ale může mít vliv na to, nevracení paměti.  
  
     Tento obrázek ukazuje snímek č. 2 a 3 snímku.  
  
     ![Pořízení snímku 2 a 3 snímku](../profiling/media/js_mem_app_snapshot3.png "JS_Mem_App_Snapshot3")  
  
11. V sadě Visual Studio, vyberte **Zastavit** zastavíte profilování.  
  
12. V sadě Visual Studio porovnejte snímky. Snímek #2 obsahuje následující informace:  
  
    -   Velikost haldy (znázorněná na červenou šipka na levé straně nahoru) se zvýšila několik KB ve srovnání s snímku č. 1.  
  
        > [!IMPORTANT]
        >  Hodnoty využití přesný paměti pro velikost haldy závisí na cíl ladění.  
  
    -   Počet objektů v haldě (znázorněná red šipka vpravo nahoru), které má vyšší ve srovnání se snímek č. 1. Jeden objekt přidala (+ 1) a byly odstraněny žádné objekty (-0).  
  
     Snímek #3 obsahuje následující informace:  
  
    -   Velikost haldy zvýšila akci o několik set bajtů ve srovnání s snímku č. 2.  
  
    -   Počet objektů v haldě, které má vyšší znovu ve srovnání s snímku č. 2. Jeden objekt přidala (+ 1) a byly odstraněny žádné objekty (-0).  
  
13. Ve 3 snímku, vyberte text odkazu na pravé straně, který zobrazuje hodnota + 1 / - 0 vedle red šipka nahoru.  
  
     ![Odkaz na jiné zobrazení objektů haldy](../profiling/media/js_mem_app_link.png "JS_Mem_App_Link")  
  
     Otevře se rozdílové informace o objektech v haldě názvem **snímku 3 - snímku č. 2**, s typy zobrazení ve výchozím nastavení. Ve výchozím nastavení můžete zobrazit seznam objektů přidaných do haldy mezi snímku č. 2 a 3 snímku.  
  
14. V **oboru** filtrovat, zvolte **objekty zbyly ze snímku č. 2**.  
  
15. Otevřete objekt HTMLDivElement v horní části stromu objektů, jak je vidět tady.  
  
     ![Počet rozdílové zobrazení objektu v haldě](../profiling/media/js_mem_app_typesdiff.png "JS_Mem_App_TypesDiff")  
  
     Toto zobrazení obsahuje užitečné informace o nevrácená paměť systému, například následující:  
  
    -   Toto zobrazení uvádí element DIV s ID `item`, a udržení velikost objektu je několik set bajtů (přesná hodnota se bude lišit).  
  
    -   Tento objekt je velikost zbývajícího objekt ze snímku č. 2 a představuje potenciální nevrácená paměť systému.  
  
     Některé aplikace tomu se v tomto okamžiku: výběr **nevracení paměti** tlačítko doporučujeme odebrat – DIV element a přidat element, takže není pravé pracují kód (tedy nevracení paměti). V další části vysvětluje, jak to opravíme.  
  
    > [!TIP]
    >  V některých případech vyhledání objektu v souvislosti s `Global` objekt může pomoci určit tento objekt. Chcete-li to provést, otevřete místní nabídku pro identifikátor a zvolte **kořeny zobrazení**.  
  
##  <a name="FixingMemory"></a>Opravit problém paměti  
  
1.  Pomocí dat zjištěné při profileru, zkontrolujte kód, který je zodpovědný za odebírání elementů DOM s ID "položka". K tomu dojde `initialize()` funkce.  
  
    ```javascript  
    function initialize() {  
  
        if (wrapper != null) {  
            elem.removeNode(true);  
        }  
    }  
    ```  
  
     `elem.removeNode(true)`případně, není pracuje správně. Zkontrolujte, jak kód je ukládání do mezipaměti v elementu DOM a najít problém; odkaz na element v mezipaměti nejsou aktualizována.  
  
2.  V souboru default.js, přidejte následující řádek kódu k funkci zatížení bezprostředně před volání `appendChild`:  
  
    ```javascript  
    elem = newDiv;  
    ```  
  
     Tento kód aktualizuje odkaz na element v mezipaměti, aby správně odebrána element když zvolíte **nevracení paměti** tlačítko. Kód dokončení pro funkci zatížení teď vypadá takto:  
  
    ```javascript  
    function load() {  
  
        wrapper = document.querySelector(".wrapper");  
  
        var newDiv = document.createElement("div");  
  
        newDiv.style.zIndex = "-1";  
        newDiv.id = "item";  
        elem = newDiv;  
  
        wrapper.appendChild(newDiv);  
    }  
    ```  
  
3.  Na **ladění** nabídky, zvolte **výkonu a Diagnostika**.  
  
4.  V **nástroje**, zvolte **paměť jazyka JavaScript**a potom zvolte **spustit**.  
  
5.  Postupujte stejným způsobem jako před tři vytváření snímků. Tady jsou shrnuté kroky:  
  
    1.  V aplikaci, vyberte **nevracení paměti** tlačítko čtyřikrát za sebou.  
  
    2.  Přepněte do sady Visual Studio a zvolte **proveďte haldy snímku** pro vytvoření snímku směrného plánu.  
  
    3.  V aplikaci, vyberte **nevracení paměti** tlačítko.  
  
    4.  Přepněte do sady Visual Studio a zvolte **proveďte haldy snímku** pro druhý snímku.  
  
    5.  V aplikaci, vyberte **nevracení paměti** tlačítko.  
  
    6.  Přepněte do sady Visual Studio a zvolte **proveďte haldy snímku** pro třetí snímku.  
  
     Snímek #3 nyní zobrazuje velikost haldy jako **žádné zvýšení** ze snímku č. 2 a objekt se počítají jako + 1 / -1, což naznačuje, že jeden objekty byla přidána, a jeden objekt byl odebrán. Toto je toto chování žádoucí.  
  
     Následující obrázek znázorňuje snímku č. 2 a 3 snímku.  
  
     ![Snímky zobrazující nevracení paměti pevné](../profiling/media/js_mem_app_fixed_snapshot3.png "JS_Mem_App_Fixed_Snapshot3")  
  
## <a name="see-also"></a>Viz také  
 [Paměť jazyka JavaScript](../profiling/javascript-memory.md)