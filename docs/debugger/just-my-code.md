---
title: Ladění kódu uživatele s pouze můj kód | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 0f0df097-bbaf-46ad-9ad1-ef5f40435079
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8fb5534d376cf1a0c60b20080df8c8bfc6ad6689
ms.sourcegitcommit: 886759fb35a88f6ef5452c5b2e33a1f71da4489a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "34851822"
---
# <a name="specify-whether-to-debug-only-user-code-using-just-my-code-in-visual-studio"></a>Určete, zda chcete ladit pouze uživatelského kódu pomocí pouze můj kód v sadě Visual Studio
Můžete nakonfigurovat Visual Studio automaticky krok přes systému, framework a jiná volání neuživatelských a sbalit těchto volání v okně zásobník volání. Funkce, která povolí nebo zakáže toto chování se nazývá *pouze můj kód*. Toto téma popisuje, jak použít pouze můj kód v projektu C#, Visual Basic, C++ a JavaScript.

Pro většinu programovacích jazyků je ve výchozím nastavení povolená pouze můj kód.
  
##  <a name="BKMK_Enable_or_disable_Just_My_Code"></a> Povolit nebo zakázat pouze můj kód  
 Chcete-li povolit nebo zakázat pouze můj kód, zvolte **nástroje > Možnosti** nabídky v sadě Visual Studio. V **ladění** > **Obecné** uzlu zvolí nebo vymaže **povolit volbu pouze vlastní kód**.
  
 ![Povolit pouze můj kód v dialogovém okně Možnosti](../debugger/media/dbg_justmycode_options.png "DBG_JustMyCode_Options")  
  
> [!NOTE]
>  **Povolit volbu pouze vlastní kód** nastavení je globální nastavení, které se použije na všechny projekty sady Visual Studio ve všech jazycích.  
  
###  <a name="BKMK_Override_call_stack_filtering"></a> Zobrazit bez uživatelského kódu v zobrazeních zásobník volání  
 V zobrazení, které se zobrazí zásobníku volání, jako **zásobníkem volání** a **úlohy** windows, pouze můj kód sbalí bez uživatelského kódu do označený poznámkou rámečku `[External Code]`. Chcete-li zobrazit sbalené rámce, zvolte **zobrazit externí kód** zobrazení v místní nabídce zásobníku volání.

 ![Zobrazit externí kód v okně zásobník volání](../debugger/media/dbg_justmycode_showexternalcode.png "DBG_JustMyCode_ShowExternalCode")
  
> [!NOTE]
>  **Zobrazit externí kód** nastavení se uložilo do profileru aktuálního uživatele. Je použito na všechny projekty ve všech jazycích, které jsou otevřené uživatelem.
  
##  <a name="BKMK__NET_Framework_Just_My_Code"></a> Rozhraní .NET framework pouze můj kód  
  
###  <a name="BKMK_NET_User_and_non_user_code"></a> Uživatel a neuživatelských kódu  
 Pouze můj kód k rozlišení uživatelského kódu z jiných uživatelského kódu, zjistí souborů symbolu (.pdb) a optimalizace programu. Ladicí program zvažuje kód jako jiný uživatelský kód při optimalizaci binárního souboru, nebo pokud na soubor .pdb není k dispozici.
  
 Ladicí program považuje na vlastní kód ovlivní také tři atributy:  
  
-   <xref:System.Diagnostics.DebuggerNonUserCodeAttribute> kód, který se použije k není vlastní kód informuje ladicího programu.  
  
-   <xref:System.Diagnostics.DebuggerHiddenAttribute> Skryje kód z ladicí program, i když je vypnuto pouze můj kód.  
  
-   <xref:System.Diagnostics.DebuggerStepThroughAttribute> informuje ladicí program na krok prostřednictvím kód, který je tato, místo kroku do kódu.  
  
 Všechny ostatní kódu se považuje za uživatelského kódu.  
  
###  <a name="BKMK_NET_Stepping_behavior"></a> Krokování s chování  
 Pokud jste **Krokovat s vnořením** (klávesové zkratky: F11) bez uživatelského kódu, ladicí program přes kód k příkazu Další uživatele. Pokud jste **Krokovat s Vystoupením** (klávesové: Shift + F11), ladicí program spouští na další řádek uživatelského kódu. Pokud je zjištěna žádná uživatelského kódu, pak provádění pokračuje v až aplikace ukončí, je stiskněte tlačítko zarážku nebo dojde k výjimce.  
  
###  <a name="BKMK_NET_Breakpoint_behavior"></a> Chování zarážek  
 Pokud je povoleno pouze můj kód, můžete **přerušení všech** (klávesové: Ctrl + Alt + Break) a zastavit provádění v umístění tam, kde není žádný kód uživatele k zobrazení. Pokud k tomu dojde, zobrazí se okno žádný zdroj. Pokud pak zvolíte příkaz kroku, ladicího programu přejdete na další řádek uživatelského kódu.  
  
###  <a name="BKMK_NET_Exception_behavior"></a> Výjimka chování  
 Pokud dojde k neošetřené výjimce v jiných uživatelského kódu, ladicího programu dělí na řádku v uživatelském kódu, kde byla vygenerována výjimka.  
  
 Pokud první možnosti výjimky jsou povolené pro výjimku, uživatelský kód řádku zvýrazní zeleně. Zásobník volání zobrazí poznámkami snímku s popisem **[externí kód]**.  
  
##  <a name="BKMK_C___Just_My_Code"></a> C++ pouze můj kód  
  
###  <a name="BKMK_CPP_User_and_non_user_code"></a> Uživatel a neuživatelských kódu  
 Pouze můj kód C++ je jiný než rozhraní .NET Framework a pouze můj kód JavaScript, protože taktování chování je nezávislé na chování zásobníku volání.  
  
 **Zásobníky volání**  
  
 Ve výchozím nastavení považuje ladicího programu tyto funkce jako jiný uživatel kódu v zásobníku volání systému windows:  
  
-   Funkce s odřapíkovaného zdroje informací v souboru jejich symboly.  
  
-   Funkce, které soubory symbolů označení, že žádný zdrojový soubor odpovídající rámce zásobníku.  
  
-   Funkce zadaný v `*.natjmc` soubory `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` složky.  
  
 **Krokování s**  
  
 Ve výchozím nastavení, pouze funkce zadaný v `*.natstepfilter` soubory `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` složky jsou považovány za bez uživatelského kódu.  
  
 Můžete vytvořit vlastní `.natstepfilter` a `.natjmc` přizpůsobit posílení a chování okno zásobník volání v `%USERPROFILE%\My Documents\Visual Studio 2017\Visualizers`.  
  
###  <a name="BKMK_CPP_Stepping_behavior"></a> Krokování s chování  
 Pokud jste **Krokovat s vnořením** (klávesové zkratky: F11) neuživatelských kód z uživatelského kódu, ladicí program přes kód na další řádek uživatelského kódu. Pokud jste **Krokovat s Vystoupením** (klávesové: Shift + F11), ladicí program spouští na další řádek uživatelského kódu. Pokud je zjištěna žádná uživatelského kódu, pak provádění pokračuje v až aplikace ukončí, je stiskněte tlačítko zarážku nebo dojde k výjimce.  
  
 Pokud ladicí program zalomení řádků kódu neuživatelských (např. Pokud přerušení všech příkaz zastaví v neuživatelských kódu), zanoříte se bude pokračovat bez uživatelského kódu.  
  
###  <a name="BKMK_CPP_Exception_behavior"></a> Výjimka chování  
 Pokud se ladicí program dotkne výjimku, zastaví v výjimky bez ohledu na to, jestli je v uživatele nebo bez uživatelského kódu. **Neošetřené uživatelem** možnosti v **výjimky** dialogové okno se ignorují.  
  
###  <a name="BKMK_CPP_Customize_stepping_behavior"></a> Přizpůsobení taktování chování  
 Můžete zadat funkce krok nepřevezme výpis je jako jiný uživatelský kód v `*.natstepfilter` soubory.  
  
-   Zadat jiný uživatelský kód pro všechny uživatele počítače Visual Studio, přidejte soubor .natstepfilter `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` složky.  
  
-   Pokud chcete zadat jiný uživatelský kód pro jednotlivé uživatele, přidání .natstepfilter soubor `%USERPROFILE%\My Documents\Visual Studio 2017\Visualizers` složky.  
  
 .natstepfilter soubory jsou soubory xml s touto syntaxí:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<StepFilter xmlns="http://schemas.microsoft.com/vstudio/debugger/natstepfilter/2010">  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Action>StepAction</Action>  
    </Function>  
    <Function>  
        <Name>FunctionSpec</Name>  
        <Module>ModuleSpec</Module>  
        <Action>StepAction</Action>  
    </Function>  
</StepFilter>  
  
```  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Funkce|Požadováno. Určuje jeden nebo více funkcí jako jiný uživatel funkce.|  
|`Name`|Požadováno. ECMA-262 ve formátu zadání názvu úplné funkce tak, aby odpovídaly regulární výraz. Příklad:<br /><br /> `<Name>MyNS::MyClass.*</Name>`<br /><br /> informuje ladicí program, který všechny metody v `MyNS::MyClass` jsou považovány bez uživatelského kódu. Porovnávání rozlišuje velká a malá písmena.|  
|`Module`|Volitelné. ECMA-262 ve formátu regulární výraz určení úplné cesty k modul, který obsahuje funkce. Shoda nerozlišuje malá a velká písmena.|  
|`Action`|Požadováno. Jednu z těchto hodnot malá a velká písmena:<br /><br /> -   `NoStepInto`  -informuje ladicí program na Krok přes odpovídající funkce.<br />-   `StepInto`  -informuje ladicí program na krok do odpovídající funkce přepsání jakékoliv `NoStepInto` pro odpovídající funkce.|  
  
###  <a name="BKMK_CPP_Customize_call_stack_behavior"></a> Přizpůsobení chování zásobník volání  
 Můžete zadat moduly, zdrojové soubory a zadáním je považovat za zařízení bez uživatelského kódu v zásobníky volání funkce `*.natjmc` soubory.  
  
-   Zadat jiný uživatelský kód pro všechny uživatele počítače Visual Studio, přidejte soubor .natjmc `%VsInstallDirectory%\Common7\Packages\Debugger\Visualizers` složky.  
  
-   Pokud chcete zadat jiný uživatelský kód pro jednotlivé uživatele, přidání .natjmc soubor `%USERPROFILE%\My Documents\Visual Studio 2017\Visualizers` složky.  
  
 .natjmc soubory jsou soubory xml s touto syntaxí:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<NonUserCode xmlns="http://schemas.microsoft.com/vstudio/debugger/jmc/2015">  
  
  <!-- Modules -->  
  <Module Name="ModuleSpec" />  
  <Module Name="ModuleSpec" Company="CompanyName" />  
  
  <!-- Files -->  
  <File Name="FileSpec"/>  
  
  <!-- Functions -->  
  <Function Name="FunctionSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" />  
  <Function Name="FunctionSpec" Module ="ModuleSpec" ExceptionImplementation="true" />  
  
</NonUserCode>  
  
```  
  
 **Element atributy modulu**  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Úplná cesta modul, nebo moduly. Můžete použít zástupné znaky Windows `?` (nula nebo jeden znak) a `*` (nula nebo více znaků). Například<br /><br /> `<Module Name="?:\3rdParty\UtilLibs\*" />`<br /><br /> informuje ladicí program na považovat všechny moduly v `\3rdParty\UtilLibs` na všechny jednotky jako externí kód.|  
|`Company`|Volitelné. Název společnosti, která publikuje modul, který se vloží do spustitelného souboru. Tento atribut slouží k rozlišení moduly.|  
  
 **Element atributy souboru**  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Úplná cesta zdrojový soubor nebo soubory považovat za externí kódu. Můžete použít zástupné znaky Windows `?` a `*` při zadání cesty.|  
  
 **Atributy prvků – funkce**  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Plně kvalifikovaný název funkce, která se považovat za externí kódu.|  
|`Module`|Volitelné. Název nebo úplnou cestu k modul, který obsahuje funkce. Tento atribut slouží k rozlišení funkce se stejným názvem.|  
|`ExceptionImplementation`|Pokud nastavíte hodnotu `true`, zobrazí se zásobníkem volání funkce, která vrátila výjimku spíše než tuto funkci.|  
  
##  <a name="BKMK_JavaScript_Just_My_Code"></a> Pouze můj kód JavaScript  
  
###  <a name="BKMK_JS_User_and_non_user_code"></a> Uživatel a neuživatelských kódu  
 **Klasifikace kódu**  
  
 Pouze můj kód JavaScript – ovládací prvky zásobníku zobrazení krokování a volání zařazením kódu v jednom z těchto klasifikací:  
  
|||  
|-|-|  
|**MyCode**|Uživatelský kód, který vlastníte a řídit.|  
|**LibraryCode**|Neuživatelských kód z vaší aplikace a knihovny, které běžně používáte spoléhá na fungovat správně (např. WinJS nebo jQuery).|  
|**UnrelatedCode**|Neuživatelských kód, který může být spuštěna v aplikaci, ale nevlastníte a vaše aplikace není přímo na ni tedy spoléhat fungovat správně. (Například to může zahrnovat advertising SDK, která zobrazuje reklamy.) V projektech UWP kód, který je načten do vaší aplikace z protokolu HTTP nebo HTTPS URI považuje také UnrelatedCode.|  
  
 Ladicí program JavaScript automaticky klasifikuje tyto typy kódu:  
  
-   Skript, který se spustí pomocí předání řetězec zadaný hostitele `eval` funkce je klasifikován jako **MyCode**.  
  
-   Skript, který je proveden předáním řetězec tak, aby `Function` konstruktor je klasifikován jako **LibraryCode**.  
  
-   Skript, který je součástí framework odkaz, jako je například WinJS nebo sady SDK Azure je klasifikován jako **LibraryCode**.  
  
-   Skript, který je proveden předáním řetězec tak, aby `setTimeout`, `setImmediate`, nebo `setInterval` funkce je klasifikován jako **UnrelatedCode**.  
  
-   `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` Určuje jiný uživatel a neuživatelských kód pro všechny projekty Visual Studio JavaScript.  
  
 Můžete upravit výchozí klasifikace a klasifikovat konkrétních souborů a adresy URL pomocí přidat soubor .json s názvem `mycode.json` ke kořenové složce projektu.  
  
 Jiný kód je klasifikován jako **MyCode**.  
  
###  <a name="BKMK_JS_Stepping_behavior"></a> Krokování s chování  
  
-   Pokud funkce není uživatelem (**MyCode**) kód, **Krokovat s vnořením** (klávesové zkratky: F11) se chová jako **Krokovat s přeskočením** (klávesové: F10).  
  
-   Pokud krok, začne v neuživatelských (**LibraryCode** nebo **UnrelatedCode**) kód, pak krokování s dočasně chová jako kdyby pouze můj kód není povoleno. Pokud krok zpět do uživatelského kódu, pouze můj kód zanoříte se je znovu zapnout.  
  
-   Při kroku ve výsledcích kód uživatele v aktuálním kontextu spuštění (například provedením kroku na posledním řádku obslužné rutiny události) a ladicí program zastaví na další řádek spuštění uživatelského kódu. Například pokud se provede zpětné volání v **LibraryCode** kód ladicí program bude pokračovat, dokud se provede na další řádek uživatelského kódu.
  
-   **Krokovat s Vystoupením** (klávesové: Shift + F11) se zastaví v dalším řádku kódu uživatele. Pokud je zjištěna žádná uživatelského kódu, pak provádění pokračuje v až aplikace ukončí, je stiskněte tlačítko zarážku nebo dojde k výjimce.  
  
###  <a name="BKMK_JS_Breakpoint_behavior"></a> Chování zarážek  
  
-   Nastavení v kódu se vždycky být zarážky bez ohledu na klasifikaci tento kód  
  
-   Pokud `debugger` – klíčové slovo se vyskytuje v:  
  
    -   **LibraryCode** kódu, ladicího programu vždy dělí.  
  
    -   **UnrelatedCode** kódu, není zastavení ladicího programu.  
  
###  <a name="BKMK_JS_Exception_behavior"></a> Výjimka chování  
 Pokud dojde k neošetřené výjimce v:  
  
-   **MyCode** nebo **LibraryCode** kódu, ladicího programu vždy dělí.  
  
-   **UnrelatedCode** kód, a **MyCode** nebo **LibraryCode** kódu je v zásobníku volání, zalomení ladicí program.  
  
 Pokud první možnosti výjimky jsou povolené pro výjimky v dialogovém okně výjimky a je vyvolána výjimka **LibraryCode** nebo **UnrelatedCode** kódu:  
  
-   Pokud je výjimka ošetřena, není přerušení ladicího programu.  
  
-   Pokud není zpracována výjimka, dělí ladicího programu.  
  
###  <a name="BKMK_JS_Customize_Just_My_Code"></a> Přizpůsobení pouze můj kód  
 Zařadit do kategorií uživatelů a jiný uživatelský kód pro jeden projekt sady Visual Studio, přidejte soubor .json s názvem `mycode.json` ke kořenové složce projektu.  
  
 Klasifikace jsou prováděny v tomto pořadí:  
  
1.  Výchozí klasifikace  
  
2.  Klasifikace v `%VSInstallDirectory%\JavaScript\JustMyCode\mycode.default.wwa.json` souboru  
  
3.  Klasifikace v `mycode. json` souboru aktuálního projektu.  
  
 Každý krok klasifikace přepíše předchozí kroky. Soubor .json nemusí seznam všech párů klíčových hodnot a **MyCode**, **knihovny**, a **Unrelated** hodnoty mohou být prázdné pole.  
  
 Moje soubory kódu .json použijte následující syntaxi:  
  
```json  
{  
    "Eval" : "Classification",  
    "Function" : "Classification",  
    "ScriptBlock" : "Classification",  
    "MyCode" : [  
        "UrlOrFileSpec",  
        . . .  
        "UrlOrFileSpec"  
    ],  
    "Libraries" : [  
        "UrlOrFileSpec",  
        . .  
        "UrlOrFileSpec"  
    ],  
    "Unrelated" : [  
        "UrlOrFileSpec",  
        . . .  
        "UrlOrFileSpec"  
    ]  
}  
  
```  
  
 **Zkušební verze, funkce, tak i vlastnost ScriptBlock**  
  
 **Eval**, **funkce**, a **ScriptBlock** párů klíčových hodnot určit, jak dynamicky je klasifikován generovaného kódu.  
  
|||  
|-|-|  
|**zkušební verze**|Skript, který se spustí pomocí předání řetězec zadaný hostitele `eval` funkce. Ve výchozím nastavení, je klasifikovaný Eval skriptu **MyCode**.|  
|**Funkce**|Skript, který je proveden předáním řetězec tak, aby `Function` konstruktor. Ve výchozím nastavení, je klasifikovaný funkce skriptu **LibraryCode**.|  
|**Blok skriptu**|Skript, který je proveden předáním řetězec tak, aby `setTimeout`, `setImmediate`, nebo `setInterval` funkce. Ve výchozím nastavení, je klasifikovaný skriptu ScriptBlock **UnrelatedCode**.|  
  
 Změňte hodnotu na jedno z klíčových slov:  
  
-   `MyCode`  klasifikuje do skriptu jako **MyCode**.  
  
-   `Library`  klasifikuje do skriptu jako **LibraryCode**.  
  
-   `Unrelated`  klasifikuje do skriptu jako **UnrelatedCode**.  
  
 **MyCode, knihovny a které nejsou**  
  
 **MyCode**, **knihovny**, a **Unrelated** párů klíčových hodnot zadejte adresy URL nebo soubory, které chcete zahrnout do klasifikaci:  
  
|||  
|-|-|  
|**MyCode**|Pole adresy URL nebo soubory, které jsou klasifikovány jako **MyCode**.|  
|**Knihovny**|Pole adresy URL nebo soubory, které jsou klasifikovány jako **LibraryCode**.|  
|**Vztah**|Pole adresy URL nebo soubory, které jsou klasifikovány jako **UnrelatedCode**.|  
  
 Řetězec adresy url nebo soubor může obsahovat jedno nebo více `*` znaky, které se shodují nula nebo více znaků. `*` odpovídá regulárnímu výrazu `.*`.
