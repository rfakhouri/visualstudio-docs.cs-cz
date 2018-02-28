---
title: "Ladění kódu HTML a CSS v aplikacích pro UPW | Microsoft Docs"
ms.custom: 
ms.date: 07/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.DomExplorer
dev_langs:
- JavaScript
helpviewer_keywords:
- debugging, CSS
- debugging, HTML
- debugging, JavaScript [UWP apps]
- DOM Explorer [UWP apps]
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- uwp
ms.openlocfilehash: bb410c6279b2910dfcb1af98ff75293d60a7e3e7
ms.sourcegitcommit: 5d43e9590e2246084670b79269cc9d99124bb3df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/19/2018
---
# <a name="debug-html-and-css-in-uwp-apps-in-visual-studio"></a>Ladění kódu HTML a CSS v aplikacích pro UPW v sadě Visual Studio
  
 Pro aplikace, JavaScript Visual Studio poskytuje komplexní ladění prostředí, které obsahuje funkce, které jsou pro vývojáře v aplikaci Internet Explorer a Visual Studio. Tyto funkce jsou podporované pro aplikace UWP a pro aplikace vytvořené pomocí nástroje sady Visual Studio pro Apache Cordova.  
  
 Použití interaktivní ladění modelu DOM kontroly nástroje poskytované můžete zobrazit a upravit kód vykreslené značky HTML a CSS. Provedete to vše bez zastavení a spuštění ladicího programu.
  
 Informace o dalších JavaScript ladění funkcí, například pomocí okna konzoly jazyka JavaScript a nastavení zarážek, najdete v části [rychlý úvod: ladění jazyka JavaScript](../debugger/quickstart-debug-javascript-using-the-console.md) a [ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md).  
  
##  <a name="InspectingDOM"></a>Probíhá kontrola za provozu DOM  
 Průzkumník modelu DOM se dozvíte, zobrazení vykreslené stránky a Průzkumníka modelu DOM můžete změnit hodnoty a okamžitě zobrazit výsledky. To umožňuje testovat změny bez zastavení a spuštění ladicího programu. Pokud při práci s stránku pomocí této metody nezmění zdrojového kódu v projektu, až najdete požadované kód opravy, provedete změny vašeho zdrojového kódu.  
  
> [!TIP]
>  Aby se zabránilo zastavením a restartováním ladicí program, když provedete změny vašeho zdrojového kódu, můžete obnovit pomocí aplikace **aplikace pro aktualizaci Windows** tlačítka na panelu nástrojů Debug (nebo stisknutím klávesy F4). Další informace najdete v tématu [aktualizace aplikace (JavaScript)](../debugger/refresh-an-app-javascript.md).  
  
 Můžete použít Průzkumníka modelu DOM na:  
  
-   Přejděte podstrom elementu DOM a prozkoumejte vykreslené kód HTML, CSS a JavaScript.  
  
-   Dynamicky upravit atributy a stylů CSS u elementů vykreslovaných a okamžitě zobrazit výsledky.  
  
-   Zkontrolujte, jak byly použity styly CSS prvky stránky a trasování pravidla, které byly použity.  
  
 Při ladění aplikace, musíte často v Průzkumníku modelu DOM. Vyberte elementy. Když vyberete element, hodnoty, které se zobrazují na kartě na pravé straně Průzkumníka modelu DOM automaticky aktualizovat tak, aby odrážela vybraný prvek v Průzkumníku modelu DOM. Jedná se o karty: **styly**, **počítané**, **rozložení**. Aplikace UWP podporovat i **události** a **změny** karty. Další informace o výběru elementy najdete v tématu [výběr elementy](#SelectingElements).  
  
> [!TIP]
>  Pokud je okno Průzkumníka modelu DOM zavřená, zvolte **ladění**>**Windows** > **Průzkumníka modelu DOM** znovu ho otevřete. Okno se zobrazí pouze během ladicí relace skriptu.  
  
 V následujícím postupu budeme věnovat procesem interaktivně ladění aplikace pomocí Průzkumníka modelu DOM. Vytvoříme aplikaci, která používá `FlipView` řízení a pak ho ladění. Aplikace obsahuje několik chyb.  
  
> [!WARNING]
>  Následující ukázkové aplikace je aplikace pro UPW. Stejné funkce jsou podporované pro Cordova, ale aplikace by být odlišné.  
  
#### <a name="to-debug-by-inspecting-the-live-dom"></a>Chcete-li ladit zkontrolováním za provozu DOM  
  
1.  Vytvořte nové řešení v sadě Visual Studio výběrem **soubor** > **nový projekt**.  
  
2.  Zvolte **JavaScript** > **univerzální pro Windows**a potom zvolte **WinJS aplikace**.  
  
3.  Zadejte název projektu, například `FlipViewApp`a zvolte **OK** k vytvoření dané aplikace.  
  
4.  V textu elementu index.html přidejte tento kód:  
  
    ```html  
    <div id="flipTemplate" data-win-control="WinJS.Binding.Template"  
             style="display:none">  
        <div class="fixedItem" >  
            <img src="#" data-win-bind="src: flipImg" />  
        </div>  
    </div>  
    <div id="fView" style="width:100px;height:100px"  
        data-win-control="WinJS.UI.FlipView" data-win-options="{  
        itemDataSource: Data.items.dataSource, itemTemplate: flipTemplate }">  
    </div>  
    ```  
  
5.  Otevřete default.css a přidejte následující CSS:  
  
    ```css  
    #fView {  
        background-color:#0094ff;  
        height: 100%;  
        width: 100%;  
        margin: 25%;  
    }  
    ```  
  
6.  Nahraďte kód v souboru default.js s tímto kódem:  
  
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
  
     Následující obrázek znázorňuje, co chcete zobrazit, pokud jsme spustit tuto aplikaci. Však získat aplikaci do tohoto stavu jsme bude mít první vyřešit počet chyb.  
  
     ![Aplikace FlipView zobrazující očekávané výsledky](../debugger/media/js_dom_appfixed.png "JS_DOM_AppFixed")  
  
7.  Zvolte **místního počítače** z rozevíracího seznamu vedle položky **spustit ladění** tlačítko **ladění** nástrojů:  
  
     ![Vyberte možnost ladění cílového seznamu](../debugger/media/js_select_target.png "JS_Select_Target")  
  
8.  Zvolte **ladění** > **spustit ladění**, nebo stiskněte klávesu F5, ke spouštění vaší aplikace v režimu ladění.  
  
     Toto spouští aplikaci, ale protože stylu má několik chyb v něm uvidíte většinou prázdnou obrazovku. První `FlipView` bitové kopie se zobrazí v Čtvereček blízko poloviny obrazovky.  
  
10. Přepněte do sady Visual Studio a zvolte **Průzkumníka modelu DOM** kartě.  
  
    > [!TIP]
    >  Stisknutím klávesy Alt + Tab nebo F12 přepínat mezi Visual Studio a spuštěné aplikaci.  
  
11. V okně Průzkumníka modelu DOM vyberte element DIV pro oddíl, který má ID `"fView"`. Chcete-li zobrazit a vybrat správný element DIV použijte klávesy se šipkami. (Klávesu šipka doprava vám umožní zobrazit podřízené položky elementu.)  
  
     ![DOM Explorer](../debugger/media/js_dom_explorer.png "JS_DOM_Explorer")  
  
    > [!TIP]
    >  Můžete také vybrat DIV element v levém dolním rohu okna konzoly jazyka JavaScript zadáním `select(fView)` na >> vstupní řádku a stisknutím klávesy Enter.  
  
     Hodnoty, které se zobrazují na kartě na pravé straně okna Průzkumníka modelu DOM automaticky aktualizovat tak, aby odrážela v Průzkumníku modelu DOM aktuálního elementu.  
  
12. Vyberte **počítané** karty na pravé straně.  
  
     Tato karta zobrazuje hodnotu počítaný nebo konečné, pro každou vlastnost vybraného elementu DOM.  
  
13. Otevřete pravidlo CSS výšku. Všimněte si, že je sadu styl vložené do 100px, která se zobrazí konzistentní s hodnota height 100 %, nastavte pro `#fView` selektor šablon stylů CSS. Text přeškrtnutí `#fView` selektor označuje styl vložené je přednost před tento styl.  
  
     Následující obrázek ukazuje **počítané** kartě.  
  
     ![Karta počítaný Průzkumníka modelu DOM](../debugger/media/js_dom_explorer_computed.png "JS_DOM_Explorer_Computed")  
  
14. V hlavním okně Průzkumníka modelu DOM dvakrát klikněte na styl vložené výšky a šířky `fView` DIV element. Nyní můžete upravit hodnoty v tomto poli. V tomto scénáři chceme je úplně odebrat.  
  
15. V hlavním okně klikněte dvakrát na `width: 100px;height: 100px;`, stiskněte **odstranit** klíče a potom stiskněte klávesu **Enter**. Po stisknutí klávesy Enter, nové hodnoty se okamžitě projeví v aplikaci, i když nejsou zastavit relaci ladění.  
  
    > [!IMPORTANT]
    >  Jak můžete aktualizovat atributy v okně Průzkumníka modelu DOM, můžete také aktualizovat hodnoty, které se zobrazují na **styly**, **počítané**, a **rozložení** karty. Další informace najdete v tématu [styly ladění šablon stylů CSS pomocí Průzkumníka modelu DOM](../debugger/debug-css-styles-using-dom-explorer.md) a [ladění rozložení pomocí Průzkumníka modelu DOM](../debugger/debug-layout-using-dom-explorer.md).  
  
16. Výběrem nebo pomocí Alt + Tab umožňuje přepnout do aplikace.  
  
     Nyní `FlipView` ovládací prvek se zobrazí větší než velikost obrazovky simulátoru nebo emulátor telefonu. Toto není určený výsledek. K prozkoumání, přepněte zpět na Visual Studio.  
  
17. V Průzkumníku modelu DOM., vyberte **počítané** kartě znovu a otevřete pravidlo výšku. FView element stále zobrazuje hodnota 100 %, podle očekávání ze šablon stylů CSS, ale vypočtená hodnota se rovná výška obrazovky aplikace (například 800px 667.67px, nebo s jinou hodnotou), což je, není co chceme pro tuto aplikaci. K prozkoumání v dalších krocích jsme odebrat výšky a šířky pro `fView` DIV element.  
  
18. V **styly** kartě a zrušte zaškrtnutí políčka vlastností výšky a šířky pro `#fView` selektor šablon stylů CSS.  
  
     **Počítané** kartě se teď zobrazují 400 px výšku. Informace označuje, že tato hodnota pochází z modulu pro výběr .win flipview zadaný v uživatelského rozhraní dark.css, což je soubor CSS platformy.  
  
19. Přepněte zpátky na aplikaci.  
  
     Co se zlepšilo. Je však stále jeden další problém vyřešit: pravého okraje se zobrazuje příliš velká.  
  
20. Chcete-li prozkoumat, přepněte do sady Visual Studio a zvolte **rozložení** a podívejte se na modelu pole elementu.  
  
     V **rozložení** karty, zobrazí se následující:  
  
    -   255px (posun) a 255px (okraje) nebo podobné hodnoty, v závislosti na rozlišení vašeho zařízení. 
  
     Následující obrázek znázorňuje jak **rozložení** karta vypadá, pokud používáte emulátor s 100px posun a okraje).  
  
     ![Karta rozložení Průzkumníka modelu DOM](../debugger/media/js_dom_explorer_layout.png "JS_DOM_Explorer_Layout")  
  
     To asi není pravé. **Počítané** kartě se zobrazují také stejné hodnoty okraj.  
  
21. Vyberte **styly** kartě a najděte `#fView` selektor šablon stylů CSS. Zde se zobrazí hodnota 25 % pro **okraj** vlastnost.  
  
22. Vyberte 25 % a změňte jej na 25px a stiskněte klávesu Enter.  
  
23. Také v **styly** kartě, vyberte pravidlo výšky pro selektor .win flipview a změňte 400 px na 500px a stiskněte klávesu Enter.  
  
24. Přepnout zpět do aplikace a zjistíte, že zobrazuje správné umístění elementů. Ujistěte se, opravy ke zdroji a aktualizujte aplikaci bez zastavení a spuštění ladicího programu, najdete v následujícím postupu.  
  
#### <a name="to-refresh-your-app-while-debugging"></a>Chcete-li aktualizovat vaši aplikaci při ladění  
  
1.  Zatímco aplikace stále běží, přepněte do sady Visual Studio.  
  
2.  Otevřete default.html a změnit změnou výška a šířka zdrojový kód `"fView"` element DIV na 100 %.  
  
3.  Vyberte **aplikace pro aktualizaci Windows** tlačítka na panelu nástrojů Debug (nebo stisknutím klávesy F4). Tlačítko vypadá takto: ![tlačítko aplikace aktualizovat Windows](../debugger/media/js_refresh.png "JS_Refresh").  
  
     Umožňuje znovu načíst stránky aplikace a Phone emulátoru nebo simulátoru vrátí do popředí.  
  
     Další informace o funkci aktualizace najdete v tématu [aktualizace aplikace (JavaScript)](../debugger/refresh-an-app-javascript.md).  
  
##  <a name="SelectingElements"></a>Výběr elementy  
 Při ladění aplikace, můžete vybrat elementů modelu DOM třemi způsoby:  
  
-   Kliknutím na elementy přímo v okně Průzkumníka modelu DOM (nebo pomocí klávesy se šipkami).  
  
-   Pomocí **vyberte Element** tlačítko (Ctrl + B).  
  
-   Pomocí `select` příkaz, který je jedním z [příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md).  
  
 Když použijete okno Průzkumníka modelu DOM vybrat elementy a umístění ukazatele myši na element, zvýrazní se odpovídající element ve spuštěné aplikaci. Musíte kliknout na na element v Průzkumníku modelu DOM. Vyberte, nebo můžete použít klávesy se šipkami zvýrazněte a vybrat prvky. Můžete také vybrat elementy ve Průzkumníka modelu DOM pomocí **vybrat element** tlačítko. Následující obrázek ukazuje **vyberte Element** tlačítko.  
  
 ![Vyberte tlačítko Element v Průzkumníku modelu DOM.](../debugger/media/js_dom_select_element_button.png "JS_DOM_Select_Element_Button")  
  
 Když kliknete na tlačítko **vybrat element** (nebo stiskněte klávesu Ctrl + B), tím, ve kterém můžete vybrat položku v Průzkumníku modelu DOM. Kliknutím ve spuštěné aplikaci změní režim výběru. Režim změny zpět do režimu Normální výběru po jedním kliknutím. Když kliknete na tlačítko **vybrat element**, aplikace je teď dostupná popředí a kurzoru změní na odráží nový režim výběru. Po kliknutí na tlačítko popsané elementu, Průzkumníka modelu DOM se vrátí do popředí pomocí zadaného elementu vybraná.  
  
 Než vyberete **vyberte Element**, můžete určit, zda chcete zvýraznit elementy ve spuštěné aplikaci přepnutím **zobrazení webové stránky označuje** tlačítko. Následující obrázek znázorňuje toto tlačítko. Označuje se zobrazí ve výchozím nastavení.  
  
 ![Zobrazení webové stránky označuje tlačítko](../debugger/media/js_dom_display_highlights_button.png "JS_DOM_Display_Highlights_Button")  
  
 Pokud zvolíte možnost označte elementy, jsou vyznačené prvky, které najedete v simulátoru. Barvy pro zvýrazněné elementy shoduje modelu pole, které se zobrazí v **rozložení** kartě Průzkumníka modelu DOM.  
  
> [!NOTE]
>  Zvýraznění elementy ukázáním je podporována pouze částečně v emulátoru Windows Phone.  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [Aktualizace aplikace (JavaScript)](../debugger/refresh-an-app-javascript.md)   
 [Ladění ovládacího prvku webového zobrazení](../debugger/debug-a-webview-control.md)   
 [Klávesové zkratky](../debugger/keyboard-shortcuts-html-and-javascript.md)   
 [Příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md)   
 [Ladění ukázkový kód HTML, CSS a JavaScript](../debugger/debug-html-css-and-javascript-sample-code.md)   
 [Podpora produktu a usnadnění přístupu](http://msdn.microsoft.com/library/tzbxw1af\(VS.120\).aspx)