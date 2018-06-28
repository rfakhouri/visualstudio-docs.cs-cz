---
title: Nástroj příkazového řádku zachytávání | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: db75b3a7-80b2-4a74-91d2-fd6e0f73b45d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2424fdcb36e9157c358ab510849a4dbb709d7e62
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057697"
---
# <a name="command-line-capture-tool"></a>Nástroj příkazového řádku pro zachytávání
DXCap.exe je nástroj příkazového řádku pro zachycení diagnostiky grafiky a přehrávání. Podporuje Direct3D – 10 až 12 Direct3D – mezi všechny funkce úrovně.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
DXCap.exe [-file filename] [-frame frames | -period periods | -manual] -c app [args...]  
DXCap.exe -p [filename] [-debug | -warp | -hw] [-config] [-rawmode]  
DXCap.exe -p [filename] -screenshot [-frame frames]  
DXCap.exe -p [filename] -toXML [xml_filename]  
DXCap.exe -v [-file filename] [-examine events] [-haltonfail | -exitonfail] [-showprogress]  
DXCap.exe -e [search_string]  
DXCap.exe -info  
```  
  
#### <a name="parameters"></a>Parametry  
 `-file` `filename`  
 V režimu zachycení (`-c`), `filename` Určuje název souboru protokolu grafiky, který je grafických informací zaznamenaná za účelem. Pokud `filename` není zadán, grafických informací se zaznamená do souboru s názvem `<appname>-<date>-<time>.vsglog` ve výchozím nastavení.  
  
 V části ověření (-v) režimu `filename` Určuje název souboru protokolu grafiky má být ověřen. Pokud `filename` není zadán, je znovu použít protokol grafiky, který byl naposledy ověřena.  
  
 `-frame` `frames`  
 V režimu zachycení `frames` určuje počet snímků, které chcete zaznamenat. První snímek je 1. Můžete zadat více snímků pomocí čárky a rozsahy adres. Například pokud `frames` je `2, 5, 7-9, 15`, pak rámců `2`, `5`, `7`, `8`, `9`, a `15` zaznamenání.  

> [!TIP]
> Použití `-frame` `manual` k určení, že rámce bude zaznamenat ručně stisknutím klávesy Print Screen. Rámce se dají zachytit při spuštění aplikace; Zastavit sběr rámců, vraťte k rozhraní příkazového řádku a stiskněte klávesu enter.  
  
 `-period` `periods`  
 V režimu zachycení `periods` určuje rozsahy dobu v sekundách, během kterých chcete zaznamenat rámce. Můžete zadat více období pomocí čárky a rozsahy adres. Například pokud `periods` je `2.1-5, 7.0-9.3`, pak rámců, které jsou generovány mezi `2.1` a `5` sekund a mezi`7` a `9.3` zaznamenání sekund.  
  
 `-c` `app` [`args...`]  
 Zaznamenejte režimu. V režimu zachycení `app` Určuje název aplikace, kterou chcete zaznamenání grafických informací z; `args...` Určuje další parametry příkazového řádku pro tuto aplikaci.  
  
 `-p` [`filename`]  
 Přehrávání režimu (`-p`). V režimu přehrávání `filename` Určuje název souboru protokolu grafiky má být přehráván zpět. Pokud `filename` není zadaný, protokol grafiky, který byl naposledy přehrání je znovu.  
  
 `-debug`  
 V režimu přehrávání `-debug` Určuje, že přehrávání měla vrstva Direct3D – ladění povoleno.  
  
 `-warp`  
 V režimu přehrávání `-warp` Určuje, že přehrávání by měla provést pomocí zobrazovací jednotky OSNOVĚ softwaru.  
  
 `-hw`  
 V režimu přehrávání `-hw` Určuje, že přehrávání by být provedena GPU hardwaru.  
  
 `-config`  
 V režimu přehrávání `-config` zobrazí informace o počítači, který se používá k zachycení souboru protokolu grafiky, pokud tyto informace se zaznamenávají do protokolu.  
  
 `-rawmode`  
 V režimu přehrávání `-rawmode` Určuje, že přehrávání by se měla provést bez úprav zaznamenané události. V rámci normálního provozu provést režimu přehrávání mírně přehrávání ladění zjednodušit a zrychlit přehrávání. Například může simulovat výstupní řetězec prohození spíš než provádění příkazů řetězu odkládacího souboru. Obvykle to není problém, ale může být nutné přehrávání dochází k výskytu tak, aby se více přesném zaznamenané události; Například můžete použít tuto možnost obnovit přes celou obrazovku vykreslování chování aplikaci, která byla zaznamenána při spuštění v režimu celé obrazovky.  
  
 `-toXML` [`xml_filename`]  
 V režimu přehrávání `xml_filename` Určuje název souboru, umístění, kam je zapisován XML reprezentaci přehrávání. Pokud `xml_filename` není zadán, reprezentaci XML je zapsán do souboru s názvem stejná jako soubor se přehrání, ale vzhledem `.xml` rozšíření.  
  
 `-v`  
 Režim ověření. V režimu ověřování zaznamenané rámce se přehrávají zpět na hardware a OSNOVĚ a jejich výsledky jsou porovnávány pomocí funkce porovnání bitové kopie. Tato funkce vám pomůže rychle identifikovat problémy ovladače, které ovlivňují vaší vykreslování.  
  
 `-examine` `events`  
 V režimu ověřování `events` určuje sadu událostí grafiky jsou porovnávány, jejichž okamžitou výsledky. Například `-examine present,draw,copy,clear` omezuje porovnání k událostem, které patří do těchto kategorií.  
  
> [!TIP]
>  Doporučujeme začít s `-examine present,draw,copy,clear` vzhledem k tomu, že to bude odhalit většiny problémů ale trvat výrazně kratší dobu, než rozsáhlejší sadu událostí. V případě potřeby můžete zadat větší nebo jinou sadu událostí ověřte tyto události a odhalit jinými druhy problémů.  
  
 `-haltonfail`  
 V režimu ověřování `-haltonfail` zastaví ověření při zjištění rozdíly mezi hardwaru a OSNOVĚ vykreslení. Ověření obnoví po stisknutí klávesy.  
  
 `-exitonfail`  
 V režimu ověřování `-exitonfail` ukončí ověření okamžitě při zjištění rozdíly mezi hardwaru a OSNOVĚ vykreslení. Program se ukončí tímto způsobem, vrátí `0` do prostředí; jinak vrátí `1`.  
  
 `-showprogress`  
 V režimu ověřování `-showprogress` zobrazí informace o průběhu relace ověřování. Zobrazí se průběh OSNOVĚ na levé straně; Zobrazí se průběh hardwaru na pravé straně.  
  
 `-e` `search_string`  
 Vytvoří výčet aplikace UWP, které jsou nainstalovány. Tyto informace můžete použít k provedení příkazového řádku zachycení s aplikace UWP.  
  
 `-info`  
 Zobrazí informace o rozhraní DLLs počítače a zachycení.  
  
## <a name="remarks"></a>Poznámky  
 DXCap.exe funguje ve třech režimech:  
  
 Zaznamenat režimu (-c)  
 Zaznamenání grafických informací z aplikace spuštěné a záznam do souboru protokolu grafiky. Možnosti snímku a formát souboru jsou stejné jako sady Visual Studio.  
  
 Přehrávání režimu (-p)  
 Přehrání dříve zaznamenaný grafiky události z existujícího souboru protokolu grafiky. Ve výchozím nastavení v okně, dojde k přehrávání i v případě, že grafiky protokolu souboru zaznamenaná z aplikace celá obrazovka. Přehrávání v celé obrazovky dojde pouze po přihlášení grafiky souboru zaznamenaná z celá obrazovka aplikace a `-rawmode` je zadán.  
  
 Režim ověření (`-v`)  
 Ověří vykreslování chování přehrávání zaznamenané rámce na hardware a OSNOVĚ a poté porovnání jejich výsledky pomocí funkce porovnání bitové kopie. Tato funkce vám pomůže rychle identifikovat problémy ovladače, které ovlivňují vaší vykreslování.  
  
 Kromě těchto režimech provede dxcap.exe dva další funkce, které neprovádět zachycení či přehrávání grafických informací.  
  
 Funkce – výčet (`-e`)  
 Zobrazí podrobnosti o aplikace UWP, které jsou nainstalovány na počítači. Tyto informace patří název balíčku a ID aplikace, která identifikovat spustitelný soubor v aplikaci UWP. K zaznamenání grafických informací z aplikace pro windows store pomocí DXCap.exe, použijte název balíčku a appid místo názvu spustitelného souboru, který se používá při zaznamenání aplikace na ploše.  
  
 (Informace o – funkce`-info)`  
 Zobrazí podrobnosti o knihovny DLL počítače a zachycení.  
  
## <a name="examples"></a>Příklady  
  
### <a name="capture-graphics-information-from-a-desktop-app"></a>Zaznamenání grafických informací z aplikace na ploše  
 Použití `-c` zadat aplikaci, ze kterého chcete zaznamenání grafických informací.  
  
```ms-dos  
DXCap.exe -c BasicHLSL11.exe  
```  
  
 Ve výchozím nastavení, je grafických informací zaznamenaných do souboru s názvem `<appname>-<date>-<time>.vsglog`. Použití `-file` zadat jiný soubor, který chcete zaznamenávat do.  
  
```ms-dos  
DXCap.exe -file regression_test_12.vsglog -c BasicHLSL11.exe  
```  
  
 Zadejte další parametry příkazového řádku na aplikaci, která jste zaznamenávání z zahrnutím po název souboru aplikace.  
  
```ms-dos  
DXCap.exe -c "C:\Program Files\Internet Explorer\iexplorer.exe" "www.fishgl.com"  
```  
  
 Příkaz v předchozím příkladu zaznamená grafických informací z plochy verzi prohlížeče Internet Explorer při zobrazení webové stránky v www.fishgl.com který používá rozhraní API WebGL k vykreslení 3D obsah.  
  
> [!NOTE]
>  Protože k němu jsou předány argumenty příkazového řádku, které se zobrazí po aplikaci, je nutné zadat argumenty určený pro DXCap.exe před použitím `-c` možnost.  
  
### <a name="capture-graphics-information-from-a-uwp-app"></a>Zaznamenání grafických informací z aplikace UWP.  
 Můžete zaznamenat grafických informací z aplikace UWP.  
  
```ms-dos  
DXCap.exe -c Microsof.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps  
```  
  
 Použití DXCap.exe k zachycení z aplikace UWP je podobný používání má zaznamenat z plochy aplikace pro Windows, ale místo toho identifikaci aplikace na ploše podle názvu souboru, je určit aplikace pro UPW tak, že její název balíčku a název nebo ID spustitelný soubor uvnitř tento balíček, které chcete  Zaznamenejte z. Aby bylo snazší a zjistěte, jak identifikovat aplikace UWP, které jsou nainstalovány na počítači, použijte `-e` možnost s DXCap.exe výčet je:  
  
```ms-dos  
DXCap.exe -e  
```  
  
 Můžete zadat volitelné hledaný řetězec pro vám pomůže vyhledat aplikaci, kterou hledáte. Pokud je zadaný řetězec hledání, zobrazí DXCap.exe aplikace UWP, jejichž název balíčku, název aplikace nebo ID aplikace odpovídat hledaný řetězec. Vyhledávání nerozlišuje velká a malá písmena.  
  
```ms-dos  
DXCap.exe -e map  
```  
  
 Výše uvedeného příkazu zobrazí aplikace UWP, které odpovídají "map"; Toto je výstup:  
  
 **Balíček "Microsoft.BingMaps":**  
 **InstallDirectory: Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe C:\Program**  
 **Úplný název: Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe**  
 **UserSID          : S-1-5-21-2127521184-1604012920-1887927527-5603533**  
 **Název: Microsoft.BingMaps**  
 **Vydavatel: CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US**  
 **Verze: 2.1.2914.1734**  
 **Launchable aplikací:**  
 **ID: AppexMaps**  
 **Exe  : C:\Program Files\WindowsApps\Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe\Map.exe**  
 **IsWWA: Ne**  
 ** AppSpec (ke spuštění): **DXCap.exe - c Microsoft.BingMaps_2.1.2914.1734_x64__8wekyb3d8bbwe,AppexMaps*** poslední řádek výstupu u každé výčtové aplikace zobrazí příkaz můžete použít k zaznamenání grafických informací z něj.  
  
### <a name="capture-specific-frames-or-frames-between-specific-times"></a>Zaznamenejte určité snímky nebo snímky mezi určitých časech.  
 Použití `-frame` k určení rámců, které chcete zachytit pomocí čárky a rozsahy adres:  
  
```ms-dos  
DXCap.exe -frame 2,5,7-9,15 -c SimpleBezier11.exe  
```  
  
 Nebo použijte `-period` určením sady času rozsahy, během které k zachycení snímků. Časových rozsahů se zadávají v sekundách a lze jej zadat více oblastí:  
  
```ms-dos  
DXCap.exe -period 2.1-5, 7.0-9.3 -c SimpleBezier11.exe  
```  
  
### <a name="capture-frames-interactively"></a>Zachycení snímků interaktivně.  
 Použití `-manual` k zachycení snímků interaktivně. Stisknutím klávesy Enter zahájíte zachycení a stisknutím klávesy Enter akci zastavit.  
  
```ms-dos  
DXCap.exe -manual -c SimpleBezier11.exe  
```  
  
### <a name="play-back-a-graphics-log-file"></a>Přehrání souboru protokolu grafiky  
 Použití `-p` přehrát dříve zaznamenaný grafiky souboru protokolu.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog  
```  
  
 Název souboru k přehrání grafiky protokolu, který jste zachytili naposledy vynechte.  
  
```ms-dos  
DXCap.exe -p  
```  
  
### <a name="play-back-in-raw-mode"></a>Přehrání v režimu raw  
 Použití `-rawmode` přehrát zaznamenané příkazy přesně tak, jak k nim došlo. V části Normální přehrávání emulovaných určité příkazy, například soubor protokolu grafiky zachyceného v celé obrazovky aplikace se budou přehrávat v okně; s povoleným režimem raw se pokusí stejný soubor přehrání na celé obrazovce.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -rawmode  
```  
  
### <a name="play-back-using-warp-or-a-hardware-device"></a>Play zpět pomocí OSNOVĚ nebo hardwarového zařízení  
 Můžete chtít vynutit přehrání zadní soubor protokolu grafiky zaznamenaná v hardwarových zařízení pro použití OSNOVĚ, nebo vynuťte přehrávání protokolu zaznamenaná v OSNOVĚ použít hardwarové zařízení. Použití `-warp` přehrávání zpět pomocí OSNOVĚ.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -warp  
```  
  
 Použití `-hw` přehrávání zpět pomocí hardwaru.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -hw  
```  
  
### <a name="validate-a-graphics-log-file-against-warp"></a>Ověřte soubor protokolu grafiky proti OSNOVĚ  
 V režimu ověření soubor protokolu grafiky přehrávání na hardware a OSNOVĚ a jsou porovnávány jejich výsledky. Můžete identifikovat chyb při vykreslování způsobených ovladače. Slouží k ověření správné fungování hardwaru grafiky proti OSNOVĚ - v.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog  
```  
  
 Ke snížení objemu porovnání, můžete zadat podmnožinu příkazy pro ověření pro porovnání a jinými příkazy budou ignorovány. Pomocí - zkontrolujte Pokud chcete zadat příkazy, jejichž výsledky, které chcete porovnat.  
  
```ms-dos  
DXCap.exe -v regression_test_12.vsglog -examine present,draw,copy,clear  
```  
  
### <a name="convert-a-graphics-log-file-to-pngs"></a>Soubor protokolu grafiky převést na formát PNG  
 K zobrazení nebo analyzovat rámců ze souboru protokolu grafiky, DXCap.exe soubory lze ukládat zaznamenané rámce jako soubor ve formátu PNG (Portable Network Graphics) bitové kopie. Použití `-screenshot` k zaznamenat v režimu přehrávání výstup rámce jako soubory PNG.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot  
```  
  
 Použití `-frame` s `-screenshot` zadáte rámce, které chcete výstup.  
  
```ms-dos  
DXCap.exe -p BasicHLSL11.vsglog -screenshot -frame 5, 7-9  
```  
  
### <a name="convert-a-graphics-log-file-to-xml"></a>Soubor protokolu grafiky převést do formátu XML  
 Ke zpracování a analýza grafických protokolů pomocí známých nástrojů, jako je FindStr nebo XSLT, můžete převést DXCap.exe soubor protokolu grafiky XML. Použití `-toXML` v režimu přehrávání převést protokolu XML, nikoli pouze zpět.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML  
```  
  
 Ve výchozím nastavení výstup XML je zapsán do souboru se stejným názvem jako protokol grafiky, ale která nebyla zadána příponu .xml. V předchozím příkladu bude mít název souboru XML **regression_test_12.xml**. Zadejte jiný název souboru XML, zadejte ho po `-toXML`.  
  
```ms-dos  
DXCap.exe -p regression_test_12.vsglog -toXML temp.xml  
```  
  
 Výsledný soubor bude obsahovat kód XML, který vypadá podobně jako tento:  
  
```xml  
<Moment value="67"/>  
<Method name="CreateDXGIFactory1" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="riid" type="IID" value="770AAE78-F26F-4DBA-A829-253C83D1B387" />  
    <Parameter name="ppFactory" type="void" handle="1" isOutput="true" />  
</Method>  
  
<Moment value="167"/>  
<Method name="D3D11CreateDevice" >  
    <Return type="HRESULT" value="S_OK" />  
    <Parameter name="pAdapter" type="IDXGIAdapter" handle="34" />  
    <Parameter name="DriverType" type="D3D_DRIVER_TYPE" value="D3D_DRIVER_TYPE_UNKNOWN" />  
    <Parameter name="Software" type="HMODULE" value="pointer" />  
    <Parameter name="Flags" type="UINT" value="0" />  
    <Parameter name="pFeatureLevels" type="D3D_FEATURE_LEVEL" arrSize="1" >  
        <Element value="D3D_FEATURE_LEVEL_11_0" />  
    </Parameter>  
    <Parameter name="FeatureLevels" type="UINT" value="1" />  
    <Parameter name="SDKVersion" type="UINT" value="7" />  
    <Parameter name="ppDevice" type="ID3D11Device" handle="35" isOutput="true" />  
    <Parameter name="pFeatureLevel" type="D3D_FEATURE_LEVEL" value="D3D_FEATURE_LEVEL_11_0" isOutput="true" />  
    <Parameter name="ppImmediateContext" type="ID3D11DeviceContext" value="nullptr" isOutput="true" />  
</Method>  
```  
  
## <a name="requirements"></a>Požadavky