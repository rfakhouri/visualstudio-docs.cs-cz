---
title: "Rychlý úvod: Ladění JavaScriptu pomocí konzoly | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.JavaScriptConsole
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- JavaScript Console
- JavaScript debugging
- debugging, JavaScript
ms.assetid: ea7adb71-52b6-4a5a-9346-98ca94b06bd7
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5aed6bc3f7cd8c258eb7f566d6843792f5949b95
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="quickstart-debug-javascript-using-the-console"></a>Rychlý úvod: Ladění JavaScriptu pomocí konzoly
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Můžete okna konzoly jazyka JavaScript využívat a ladit aplikace UPW, které jsou vytvořené pomocí jazyka JavaScript. Tyto funkce jsou podporované pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace, Windows Phone aplikace a aplikace vytvořené pomocí nástrojů Visual Studio pro Apache Cordova. Informace o příkazech konzoly, najdete v části [příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md).  
  
 V okně konzoly JavaScript umožňuje:  
  
-   Odeslat objekty, hodnoty a zprávy z vaší aplikace do okna konzoly.  
  
-   Zobrazovat a upravovat hodnoty místní a globální proměnné ve spuštěné aplikaci.  
  
-   Zobrazení vizualizérech objektu.  
  
-   Kód jazyka JavaScript, který se spustí v aktuálním kontextu skript spustíte.  
  
-   Zobrazit chyby jazyka JavaScript a výjimkami, kromě Document Object (Model DOM) a prostředí Windows Runtime výjimky.  
  
-   Proveďte další úlohy, jako je vymazání obrazovky. V tématu [příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md) pro kompletní seznam příkazů.  
  
 V tomto tématu:  
  
-   [Ladění pomocí okna konzoly jazyka JavaScript](#InteractiveConsole)  
  
-   [Interaktivní režim ladění a rozdělení](#InteractiveDebuggingBreakMode)  
  
-   [Režim jeden řádek a víceřádkový režim v okně konzoly jazyka JavaScript](#SinglelineMultilineMode)  
  
-   [Přepínání kontext provádění skriptu](#Switching)  
  
> [!TIP]
>  Pokud je zavření okna konzoly jazyka JavaScript, zvolte **ladění**>**Windows** > **konzoly pro JavaScript** znovu ho otevřete. Okno se zobrazí pouze během ladicí relace skriptu.  
  
 Používání okna konzoly jazyka JavaScript, můžete pracovat s vaší aplikací bez zastavení a spuštění ladicího programu. Další informace najdete v tématu [aktualizace aplikace (JavaScript)](../debugger/refresh-an-app-javascript.md). Informace o dalších JavaScript ladění funkcí, například pomocí Průzkumníka modelu DOM a nastavení zarážek, najdete v části [rychlý úvod: ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md) a [ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md).  
  
##  <a name="InteractiveConsole"></a>Ladění pomocí okna konzoly jazyka JavaScript  
 Následující kroky slouží k vytvoření `FlipView` aplikace a ukazují, jak interaktivně ladění JavaScriptu kódování chyby.  
  
> [!CAUTION]
>  Ukázková aplikace je aplikace pro UPW. Funkce konzoly zde popsané však také použít pro aplikace vytvořené pomocí nástrojů Visual Studio pro Apache Cordova.  
  
#### <a name="to-debug-javascript-code-in-the-flipview-app"></a>Chcete-li ladit kód jazyka JavaScript v aplikaci FlipView  
  
1.  Vytvořte nové řešení v sadě Visual Studio výběrem **soubor** > **nový projekt**.  
  
2.  Zvolte **JavaScript** > **aplikacích pro Store**, vyberte buď **aplikací pro Windows** nebo **aplikace Windows Phone**a potom zvolte  **Prázdná aplikace**.  
  
3.  Zadejte název projektu, například `FlipViewApp`a zvolte **OK** k vytvoření dané aplikace.  
  
4.  V textu elementu default.html nahraďte existující kód HTML s tímto kódem:  
  
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
  
5.  Otevřete default.css a přidejte šablon stylů CSS pro `#fView` selektor:  
  
    ```css  
    #fView {  
        background-color:#0094ff;  
        height: 500px;  
        margin: 25px;  
    }  
    ```  
  
6.  Otevřete default.js a nahraďte následující kód v JavaScriptu kód:  
  
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
  
            pages.push(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
            pages.push(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
            pages.push(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
  
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
  
7.  Pokud ladění cíl již není vybrána, vyberte **simulátoru** nebo pro Windows Phone, **emulátoru 8.1 WVGA 4 palce 512MB** z rozevíracího seznamu vedle položky **zařízení** tlačítko **ladění** nástrojů:  
  
     ![Vyberte možnost ladění cílového seznamu](../debugger/media/js_select_target.png "JS_Select_Target")  
  
8.  Stisknutím klávesy F5 spuštění ladicího programu.  
  
     Chybí aplikace běží, ale bitové kopie. Vyskytly se chyby APPHOST v okně konzoly pro JavaScript chybí obrázky.  
  
9. S `FlipView` aplikace běžící v simulátoru nebo Phone emulátoru, typ `Data.items` v konzole okno vstupní řádku (vedle ">>" symbol) a stiskněte klávesu Enter.  
  
     Vizualizér pro `items` objektu se zobrazí v okně konzoly. Znamená to, že `items` objektu vytvořeny a je k dispozici v aktuálním kontextu skriptu. V okně konzoly můžete kliknout na prostřednictvím uzlů objektu k zobrazení hodnot vlastností (nebo použijte klávesy se šipkami). Pokud kliknete na `items._data` objekt, jak je vidět na tomto obrázku, zjistíte, že odkazů na zdroj bitové kopie jsou nesprávné, podle očekávání. Výchozí Image (logo.png) jsou stále přítomen v objektu a neexistují chybí obrázky spolu s očekávanou bitové kopie.  
  
     ![Okna konzoly jazyka JavaScript](../debugger/media/js_console_window.png "JS_Console_Window")  
  
     Všimněte si, že existuje mnoho více položek v `items._data` objektu než byste očekávali.  
  
10. Na příkazovém řádku zadejte `Data.items.push` a stiskněte klávesu Enter. V okně konzoly zobrazí vizualizér pro `push` funkce, které je implementované v [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] souboru projektu. V této aplikaci používáme `push` přidáte správné položky. S malým množstvím šetření pomocí IntelliSense, nám zjistit, že jsme pomocí `setAt` nahradit výchozí Image.  
  
11. Chcete-li tento problém vyřešit interaktivně bez zastavení relaci ladění, otevřete default.js a vyberte tento kód z `updateImages` funkce:  
  
    ```javascript  
    pages.push(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
    pages.push(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
    pages.push(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
    ```  
  
     Zkopírujte a vložte tento kód do konzoly pro JavaScript vstupní řádku.  
  
    > [!TIP]
    >  Pokud můžete vložit více řádků kódu do konzoly pro JavaScript vstupní řádku, řádku konzoly vstup se automaticky nepřepne do víceřádkového režimu. Stisknutím klávesy Ctrl + Alt + M zapnout víceřádkového režimu a vypnout. Chcete-li spustit skript v víceřádkového režimu, stiskněte klávesy Ctrl + Enter nebo zvolte symbol šipku v pravém dolním rohu okna. Další informace najdete v tématu [režimu a v okně konzoly pro JavaScript víceřádkového režimu](#SinglelineMultilineMode).  
  
12. Opravte `push` volání funkce na řádku nahraďte `pages.push` s `Data.items.setAt`. Opravené kód by měl vypadat takto:  
  
    ```javascript  
    Data.items.setAt(0, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223195" });  
    Data.items.setAt(1, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223196" });  
    Data.items.setAt(2, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
    ```  
  
    > [!TIP]
    >  Pokud chcete použít `pages` objektu místo `Data.items`, je třeba nastavit zarážky v kódu zachovat `pages` objekt v oboru.  
  
13. Zvolte zelenou šipku symbol pro spuštění skriptu.  
  
14. Stiskněte klávesu Ctrl + Alt + M řádku konzoly vstupní přepnout do jednořádkového režimu, a pak vyberte **vymazat vstup** (červený "X") se odstranit kód z příkazového řádku vstupní.  
  
15. Typ `Data.items.length = 3` v příkazovém řádku a potom stiskněte klávesu Enter. Tím se odebere nadbytečné elementy z data.  
  
16. Znovu zkontrolujte simulátoru nebo emulátoru telefon a uvidíte, že správné bitové kopie jsou na správný `FlipView` stránky.  
  
17. V Průzkumníku modelu DOM. uvidíte aktualizovaný element DIV a můžete přejít do podstrom najít očekávané IMG elementy.  
  
18. Zastavte ladění výběrem **ladění** > **Zastavte ladění** nebo pomocí kláves Shift + F5 a pak opravte zdrojový kód.  
  
     Pro dokončení default.html stránku obsahující opravíte ukázkový kód, najdete v části [ladění HTML, CSS a JavaScript ukázkový kód](../debugger/debug-html-css-and-javascript-sample-code.md).  
  
##  <a name="InteractiveDebuggingBreakMode"></a>Interaktivní režim ladění a rozdělení  
 Můžete použít zarážky a kroku do kódu při používání nástroje, například okna konzoly jazyka JavaScript ladění jazyka JavaScript. Pokud program, který běží v ladicím programu narazí na zarážku, ladicí program dočasně pozastaví spuštění programu. Při spouštění je pozastaveno, váš program přepíná z režimu spuštění do režimu pozastavení. Můžete obnovit provádění kdykoli.  
  
 Při spuštění programu v režimu pozastavení, můžete spouštět skripty a příkazy, které jsou platné v aktuálním kontextu spuštění skriptu okna konzoly jazyka JavaScript. V tomto postupu budete používat pevné verze `FlipView` aplikace, které jste vytvořili dříve ukazují použití režimu pozastavení.  
  
#### <a name="to-set-a-breakpoint-and-debug-the-app"></a>K nastavení boru přerušení a ladění aplikace  
  
1.  V souboru default.html `FlipView` aplikaci, která dříve vytvořili, otevřete místní nabídku pro `updateImages()` fungovat a potom vyberte **zarážek** > **vložit zarážku**.  
  
2.  Zvolte **místního počítače** nebo **emulátoru 8.1 WVGA 4 palce 512MB** v rozevíracího seznamu vedle položky **spustit ladění** tlačítko **ladění** panel nástrojů.  
  
3.  Zvolte **ladění** > **spustit ladění**, nebo stiskněte klávesu F5.  
  
     Aplikace přejde do režimu pozastavení při provádění dosáhne `updateImages()` funkce a aktuálního řádku spuštění programu zvýrazněn žlutě.  
  
     ![Režim pozastavení pomocí konzoly pro JavaScript](../debugger/media/js_breakmode.png "JS_BreakMode")  
  
     Můžete změnit hodnoty proměnných okamžitě bez ukončení aktuální relaci ladění ovlivnit stav programu.  
  
4.  Typ `updateImages` na řádku a stiskněte klávesu Enter. Vizualizér pro funkci se zobrazí v okně konzoly.  
  
5.  Vyberte funkci, v okně konzoly zobrazíte implementace funkce.  
  
     Následující obrázek znázorňuje v tomto okamžiku v okně konzoly.  
  
     ![Okna konzoly jazyka JavaScript zobrazující vizualizéru](../debugger/media/js_console_function_visualizer.png "JS_Console_Function_Visualizer")  
  
6.  Zkopírujte jeden řádek funkce v okně výstup do příkazového řádku vstupní a změňte hodnotu indexu na 3:  
  
    ```javascript  
    pages.setAt(3, { flipImg: "http://go.microsoft.com/fwlink/?LinkID=223197" });  
    ```  
  
7.  Stiskněte klávesu Enter pro spuštění na řádek kódu.  
  
     Pokud chcete pro jednotlivé řádky kódu kroky, stiskněte klávesu F11 nebo stiskněte klávesu F5, chcete-li pokračovat spuštění programu.  
  
8.  Stisknutím klávesy F5 pokračovat spuštění programu. `FlipView` Aplikace se zobrazí, a teď všechny čtyři stránky zobrazí jednu z imagí jiné než výchozí.  
  
     Chcete-li přepnout zpět do Visual Studio, stiskněte klávesu F12 nebo Alt + Tab.  
  
##  <a name="SinglelineMultilineMode"></a>Režim jeden řádek a víceřádkový režim v okně konzoly jazyka JavaScript  
 Vstupní řádku okna konzoly jazyka JavaScript podporuje víceřádkového režimu i režimu. Interaktivní ladění postup v tomto tématu poskytuje příklad použití oba režimy. Stisknutím klávesy Ctrl + Alt + M pro přepínání mezi režimy.  
  
 Režim jeden řádek představuje vstupní historie. Vstupní historie můžete procházet pomocí klávesy šipka nahoru a Šipka dolů. Jeden řádek režimu vymaže vstupní řádku při spouštění skriptů. Chcete-li spustit skript v režimu jeden řádek, stiskněte klávesu Enter.  
  
 Víceřádkového režimu nevymaže vstupní řádku při spouštění skriptů. Když jste přešli do režimu jeden řádek z víceřádkového režimu, můžete vymazat vstupní řádku stisknutím kombinace kláves **vymazat vstup** (červený "X"). Chcete-li spustit skript v víceřádkového režimu, stiskněte klávesy Ctrl + Enter nebo zvolte symbol šipku v pravém dolním rohu okna.  
  
##  <a name="Switching"></a>Přepínání kontext provádění skriptu  
 V okně konzoly jazyka JavaScript umožňuje pracovat s jednoho spuštění kontext, který představuje jednu instanci hostitele webové platformy (WWAHost.exe), v čase. V některých scénářích může aplikace začít jiná instance hostitele, například při použití `iframe`, kontraktu sdílenou složku, pracovní web, nebo `WebView` ovládacího prvku. Pokud je spuštěna jiná instance hostitele, můžete vybrat jiný provádění kontextu při spuštění aplikace tak, že vyberete kontext spuštění v **cíl** seznamu.  
  
 Následující obrázek znázorňuje seznamu cíl v okně konzoly jazyka JavaScript.  
  
 ![Cíl výběr v okně konzoly jazyka JavaScript](../debugger/media/js_console_target.png "JS_Console_Target")  
  
 Také můžete přepnout kontext spuštění pomocí `cd` příkaz, ale musíte znát název jiné kontextu spuštění a odkaz použijete musí být v rozsahu. **Cíl** seznamu poskytuje lepší přístup do jiných kontextech provádění.  
  
##  <a name="BrowserSupport"></a>Prohlížeče a podporu platforem  
 V okně konzoly jazyka JavaScript se podporuje na následujících platformách:  
  
-   [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]a aplikace pro Windows Phone pomocí jazyka JavaScript a HTML  
  
-   Internet Explorer 11 a systémem[!INCLUDE[win81](../debugger/includes/win81_md.md)]  
  
-   Internet Explorer 10 systémem[!INCLUDE[win8](../debugger/includes/win8_md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Ladění aplikací v sadě Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)   
 [Příkazy konzoly pro JavaScript](../debugger/javascript-console-commands.md)   
 [Aktualizace aplikace (JavaScript)](../debugger/refresh-an-app-javascript.md)   
 [Klávesové zkratky](../debugger/keyboard-shortcuts-html-and-javascript.md)   
 [Ladění ukázkový kód HTML, CSS a JavaScript](../debugger/debug-html-css-and-javascript-sample-code.md)   
 [Rychlý úvod: Ladění kódu HTML a CSS](../debugger/quickstart-debug-html-and-css.md)   
 [Ladění ovládacího prvku webového zobrazení](../debugger/debug-a-webview-control.md)   
 [Podpora produktu a usnadnění přístupu](http://msdn.microsoft.com/library/tzbxw1af\(VS.120\).aspx)