---
title: 'Návod: Vytvoření sady SDK, pomocí jazyka JavaScript | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: a8c89d5d-5b78-4435-817f-c5f25ca6d715
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2132269329c8b6af3ac846596adea7b3462db5bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144213"
---
# <a name="walkthrough-creating-an-sdk-using-javascript"></a>Návod: Vytvoření sady SDK, pomocí jazyka JavaScript
Tento názorný postup učí, jak vytvořit jednoduché matematické SDK jako Visual Studio rozšíření (VSIX) pomocí jazyka JavaScript.  Průvodce se dělí na tyto části:  
  
-   [Vytvoření projektu SimpleMathVSIX rozšíření sady SDK](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSimpleMathVSIX)  
  
-   [K vytvoření ukázkové aplikace, která využívá SDK](../extensibility/walkthrough-creating-an-sdk-using-javascript.md#createSampleApp)  
  
 Pro jazyk JavaScript neexistuje žádný typ projektu knihovny tříd. V tomto návodu je ukázkový soubor arithmetic.js vytvořené přímo v projektu VSIX. V praxi, doporučujeme vám nejdřív sestavení a testů souborů JavaScript a CSS jako aplikace pro Windows Store – například pomocí **prázdnou aplikaci** šablony – předtím, než začleníte v projektu VSIX.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createSimpleMathVSIX"></a> Vytvoření projektu SimpleMathVSIX rozšíření sady SDK  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V seznamu kategorií šablony v části **Visual C#**, vyberte **rozšiřitelnost**a pak vyberte **projektu VSIX** šablony.  
  
3.  V **název** text zadejte `SimpleMathVSIX` a zvolte **OK** tlačítko.  
  
4.  Pokud **průvodce balíčku sady Visual Studio** se zobrazí, vyberte **Další** na tlačítko **úvodní** stránky a pak na **stránka 1, 7**, vyberte **Dokončit** tlačítko.  
  
     I když **Návrhář manifestu** otevře, jsme budete zjednodušení Tento názorný postup úpravou souboru manifestu přímo.  
  
5.  V **Průzkumníku řešení**, otevřete místní nabídku pro soubor source.extension.vsixmanifest a potom zvolte **kód zobrazení**. Pomocí tohoto kódu nahradit existující obsah v souboru.  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
      <Metadata>  
        <Identity Id="SimpleMathVSIX" Version="1.0" Language="en-US" Publisher="myname" />  
        <DisplayName>Simple Math</DisplayName>  
        <Description>Does basic arithmetic calculations.</Description>  
      </Metadata>  
      <Installation Scope="Global" AllUsers="true">  
        <InstallationTarget Id="Microsoft.ExtensionSDK" TargetPlatformIdentifier="Windows" TargetPlatformVersion="v8.0" SdkName="SimpleMath" SdkVersion="1.0" />  
      </Installation>  
      <Dependencies>  
        <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="4.5" />  
      </Dependencies>  
      <Assets>  
        <Asset Type="Microsoft.ExtensionSDK" d:Source="File" Path="SDKManifest.xml" />  
      </Assets>  
    </PackageManifest>  
    ```  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídky projektu SimpleMathVSIX a potom zvolte **přidat**, **novou položku**.  
  
7.  V **Data** kategorie, vyberte **souboru XML**, název souboru `SDKManifest.xml`a vyberte **přidat** tlačítko.  
  
8.  V **Průzkumníku řešení**, otevřete místní nabídku pro soubor SDKManifest.xml a potom zvolte **otevřete** zobrazit soubor v **editoru XML**.  
  
9. Přidejte následující kód do souboru SDKManifest.xml.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <FileList  
      DisplayName="Simple Math"  
      MinVSVersion="14.0"  
      AppliesTo="JavaScript+WindowsAppContainer"  
      SupportsMultipleVersions="Error"  
      MoreInfo="http://www.msdn.microsoft.com/">  
  
      <!-- JS -->  
      <File Content="js\arithmetic.js" />  
    </FileList>  
  
    ```  
  
10. V **Průzkumníku řešení**, v místní nabídce souboru SDKManifest.xml, zvolte **vlastnosti**.  
  
11. V **vlastnosti** nastavte **zahrnout do VSIX** vlastnost **True**.  
  
12. V **Průzkumníku řešení**, v místní nabídce pro projekt SimpleMathVSIX, zvolte **přidat**, **novou složku**a zadejte název složky `Redist`.  
  
13. Přidejte podsložky Redist vytvořit tuto strukturu:  
  
     \Redist\CommonConfiguration\Neutral\SimpleMath\js\  
  
14. V místní nabídce \js\ složky, vyberte **přidat**, **novou položku**.  
  
15. V části **Visual C# položky**, vyberte **webové** kategorie a potom vyberte **soubor JavaScript** položky. Název souboru `arithmetic.js`a potom zvolte **přidat** tlačítko.  
  
16. Vložte následující kód do arithmetic.js:  
  
    ```  
    (function (global) {  
        "use strict";  
        global.Arithmetic = {  
            add: function (firstNumber, secondNumber) {  
                return firstNumber + secondNumber;  
            },  
  
            subtract: function (firstNumber, secondNumber) {  
                return firstNumber - secondNumber;  
            },  
  
            multiply: function (firstNumber, secondNumber) {  
                return firstNumber * secondNumber;  
            },  
  
            divide: function (firstNumber, secondNumber) {  
                return firstNumber / secondNumber;  
            }  
        };  
    })(this);  
  
    ```  
  
17. V **Průzkumníku řešení**, v místní nabídce souboru arithmetic.js, zvolte **vlastnosti**. Proveďte tyto změny vlastnosti:  
  
    -   Nastavte **zahrnout do VSIX** vlastnost **True**.  
  
    -   Nastavte **kopírovat do výstupního adresáře** vlastnost **kopie vždy**.  
  
18. V **Průzkumníku řešení**, v místní nabídce pro projekt SimpleMathVSIX, zvolte **sestavení**.  
  
19. Po úspěšném dokončení sestavení v místní nabídce projektu, zvolte **otevřít složku v Průzkumníku souborů**. Přejděte do \bin\debug\\a spusťte `SimpleMathVSIX.vsix` k její instalaci.  
  
20. Vyberte **nainstalovat** tlačítko a umožňují dokončení instalace.  
  
21. Restartujte sadu Visual Studio.  
  
##  <a name="createSampleApp"></a> K vytvoření ukázkové aplikace, která využívá SDK  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V seznamu kategorií šablony v části **JavaScript**, vyberte **Windows Store**a pak vyberte **prázdnou aplikaci** šablony.  
  
3.  V **název** zadejte `ArithmeticUI`. Vyberte **OK** tlačítko.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídky projektu ArithmeticUI a potom zvolte **přidat**, **odkaz**.  
  
5.  V části **Windows**, zvolte **rozšíření**a Všimněte si, že **jednoduché matematické** se zobrazí.  
  
6.  Vyberte **jednoduché matematické** zaškrtněte políčko a zvolte **OK** tlačítko.  
  
7.  V **Průzkumníku řešení**v části **odkazy**, Všimněte si, že **jednoduché matematické** se zobrazí odkaz. Rozbalte ho a Všimněte si, že je složka \js\, která zahrnuje arithmetic.js. Můžete otevřít arithmetic.js potvrďte, že byl nainstalován vašeho zdrojového kódu.  
  
8.  Použijte následující kód k nahrazení obsah default.htm.  
  
    ```  
    <!DOCTYPE html>  
    <html>  
    <head>  
        <meta charset="utf-8" />  
        <title>ArithmeticUI</title>  
  
        <!-- WinJS references -->  
        <link href="//Microsoft.WinJS.1.0/css/ui-dark.css" rel="stylesheet" />  
        <script src="//Microsoft.WinJS.1.0/js/base.js"></script>  
        <script src="//Microsoft.WinJS.1.0/js/ui.js"></script>  
  
        <!-- ArithmeticUI references -->  
        <link href="/css/default.css" rel="stylesheet" />  
        <script src="/js/default.js"></script>  
        <script src="/SimpleMath/js/arithmetic.js"></script>  
    </head>  
    <body>  
        <form>  
        <div id="calculator" class="ms-grid">  
            <input name="firstNumber" id="firstNumber" type="number" step="any">  
            <div id="operators">  
                <button class="operator" type="button">+</button>  
                <button class="operator" type="button">-</button>  
                <button class="operator" type="button">*</button>  
                <button class="operator" type="button">/</button>  
            </div>  
            <input id="secondNumber" type="number">  
            <button class="calculate" type="button">=</button>  
            <input id="result" type="number" name="result" disabled="" readonly="">  
        </div>  
        </form>  
    </body>  
    </html>  
    ```  
  
9. Další kód použijte k nahrazení obsah \js\default.js.  
  
    ```  
    (function () {  
        "use strict";  
  
        var app = WinJS.Application;  
        var operation = null;  
  
        function calculateResult() {  
            var firstNumber = parseFloat(document.querySelector("#firstNumber").value),  
                secondNumber = parseFloat(document.querySelector("#secondNumber").value),  
                result = 0;  
  
            if (isNaN(firstNumber) || isNaN(secondNumber)) {  
                result = 0;  
            }  
            else {  
                switch (operation) {  
                    case "+":  
                        result = Arithmetic.add(firstNumber, secondNumber);  
                        break;  
                    case "-":  
                        result = Arithmetic.subtract(firstNumber, secondNumber);  
                        break;  
                    case "*":  
                        result = Arithmetic.multiply(firstNumber, secondNumber);  
                        break;  
                    case "/":  
                        result = Arithmetic.divide(firstNumber, secondNumber);  
                        break;  
                    default:  
                }  
            }  
            document.querySelector("#result").value = result.toString();  
        }  
  
        app.onactivated = function (args) {  
            document.querySelector("#calculator").addEventListener("click", function (event) {  
                if (event.target.tagName.toLowerCase() === "button") {  
                    switch (event.target.className) {  
                        case "operator":  
                            operation = event.target.innerText;  
                            break;  
                        case "calculate":  
                            calculateResult();  
                            break;  
                        default:  
                            break;  
                    }  
                }  
            });  
        };  
  
        app.start();  
    })();  
    ```  
  
10. Obsah \css\default.css nahraďte tento kód:  
  
    ```  
    form {  
        display: -ms-grid;  
        -ms-grid-rows: 1fr auto 1fr;  
        -ms-grid-columns: 1fr auto 1fr;  
        height: 100%;  
        width: 100%;  
    }  
  
    button, input[type=number] {  
        margin-right: 5px;  
        -ms-grid-row-align: center;  
    }  
  
    #calculator {  
        -ms-grid-column: 2;  
        -ms-grid-row: 2;  
        display: -ms-grid;  
        -ms-grid-rows: 1fr;  
        -ms-grid-columns: auto min-content auto auto auto;  
    }  
  
    .ms-grid input {  
        width: 5em;  
    }  
  
    #firstNumber {  
        -ms-grid-column: 1;  
        -ms-grid-row-align: center;  
    }  
  
    #operators {  
        -ms-grid-column: 2;  
        -ms-grid-row-align: center;  
    }  
  
        #operators button.operator {  
            margin-bottom: 5px;  
            height: 40px;  
        }  
  
    #secondNumber {  
        -ms-grid-column: 3;  
    }  
  
    button.calculate {  
        -ms-grid-column: 4;  
        -ms-grid-row-align: center;  
        height: 40px;  
    }  
  
    #result {  
        -ms-grid-column: 5;  
    }  
  
    ```  
  
11. Zvolte klávesy F5 sestavení a spuštění aplikace.  
  
12. V aplikaci uživatelského rozhraní, zadejte všechny dvou čísel, vyberte operace a potom zvolte **=** tlačítko. Se zobrazí správný výsledek.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření sady SDK (Software Development Kit)](../extensibility/creating-a-software-development-kit.md)