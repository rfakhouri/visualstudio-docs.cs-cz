---
redirect_url: shell/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file
title: "Úprava izolované prostředí pomocí. Soubor Pkgdef | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, isolated mode, .pkgdef file
ms.assetid: 69e8f78e-bcf1-46cb-8866-7de37d134997
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: addeeaa294a81acce6558feb5257fee1344532f8
ms.sourcegitcommit: 9a2f937e42305db6e3eaa7aadc235b0ba9aafc83
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/31/2018
---
# <a name="modifying-the-isolated-shell-by-using-the-pkgdef-file"></a>Úprava izolované prostředí pomocí. Soubor Pkgdef
Soubor .pkgdef podporuje nastavení, které můžete použít k přizpůsobení izolované prostředí aplikace. Určuje hodnoty, které se vytvoří při instalaci aplikace na počítači a který se odkazuje prostředí sady Visual Studio, když se spustí aplikace. Nastavení jsou uspořádány do souboru na základě klíčů registru použít.  
  
> [!WARNING]
>  Všimněte si, že nejsou .pkgdef soubory, které nejsou deklarován v souboru .vsixmanifest VSPackage prohledávány při spuštění sady Visual Studio.  
  
 Soubor .pkgdef obsahuje oddíly, které jsou všechny určené pomocí klíče, buď `[$RootKey$]` nebo `[$RootKey$\` *podklíč*`]`, kde $RootKey$ je kořenový klíč pro aplikaci.  
  
 Každý oddíl obsahuje dvojice název/hodnota, které mají tento formát: `"` *název hodnoty*`"=`*hodnotu*.  
  
 Hodnoty jsou buď řetězec, který je uzavřena v uvozovkách, nebo 32bitové celé číslo, která je reprezentována jako typu dword. Hodnoty mají následující omezení:  
  
-   Všechny hodnoty dword jsou v šestnáctkovém formátu, například `dword:00000001`.  
  
     Logické hodnoty 1 představuje hodnotu true a hodnota 0 představuje hodnotu false.  
  
-   Všechny GUID řetězce jsou ve formátu registru, například `"{00000000-0000-0000-0000-000000000000}"`.  
  
-   Všechny identifikátory lokalizovatelný prostředků mají tvar "@*resourceID*" nebo "#*resourceID*", kde *resourceID* je identifikátor prostředku v balíčku uživatelského rozhraní aplikace, například `"@102"`. Balíček aplikace uživatelského rozhraní je balíček, který se odkazuje v AppLocalizationPackage nastavení.  
  
 Například  
  
```  
"HideSolutionConcept"=dword:00000001  
"DefaultDebugEngine"="{00000000-0000-0000-0000-000000000000}"  
```  
  
 Komentáře můžete přidat do souboru .pkgdef. Komentář jeden řádek obsahuje dvě lomítka jako první dva znaky.  
  
 Seznam náhradní řetězce, naleznete v části [náhradní řetězce používány. Pkgdef a. Soubory Pkgundef](../extensibility/substitution-strings-used-in-dot-pkgdef-and-dot-pkgundef-files.md).  
  
 Následující části popisují konkrétní hodnoty registru ovlivňující chování prostředí sady Visual Studio v izolovaném režimu. Můžete také definovat další hodnoty registru pro aplikace v tomto souboru.  
  
> [!NOTE]
>  Pokud nastavení není k dispozici v souboru .pkgdef, se provádí žádný odpovídající záznam v registru.  
  
## <a name="settings"></a>Nastavení  
 Následující tabulka popisuje hodnot fronty definovaných v části [$RootKey$].  
  
|Název|Typ|Hodnota|  
|----------|----------|-----------|  
|AddinsAllowed|DWORD|Hodnota TRUE, pokud je možné načíst doplňky; jinak hodnota false.<br /><br /> Výchozí hodnota je true.|  
|AllowsDroppedFilesOnMainWindow|DWORD|Hodnota TRUE, pokud hlavní okno může přijmout vynechaných soubory; jinak hodnota false. Otevření souborů vyřadit v hlavní okno pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenDocumentViaProject%2A> metoda. Jde o ekvivalent otevření dokumentu s použitím **otevřete** příkaz na **souboru** nabídky v aplikaci.<br /><br /> Výchozí hodnota je true.|  
|AppIcon|odkazy řetězců|Úplná cesta ikonu programu. Tato ikona se zobrazí v záhlaví nalevo od názvu aplikace.<br /><br /> Výchozí hodnota je "$RootFolder$\\*název řešení solutionName*.ico, který", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|AppLocalizationPackage|odkazy řetězců|Identifikátor GUID VSPackage, který obsahuje satelitní sestavení uživatelského rozhraní pro aplikaci. Tato VSPackage zahrnuje kompilované verzi souboru .vsct a může obsahovat jiné lokalizovaných řetězců. Funkce sadách a skupinách příkaz nabídky můžete povolit nebo zakázat změnou nastavení v souboru projektu .vsct uživatelského rozhraní.<br /><br /> Výchozí hodnota je "{*vsUiPackageGuid*}", kde *vsUiPackageGuid* je identifikátor GUID přiřazený k balíčku aplikace uživatelského rozhraní.|  
|AppName|odkazy řetězců|Název aplikace. Název se zobrazí v záhlaví okna aplikace.<br /><br /> Výchozí hodnota je název souboru řešení aplikace.|  
|CommandLineLogo|odkazy řetězců|Text hlavičky, když je aplikace spuštěna v okně konzoly. Toto nastavení má vliv pouze aplikace, které podporují operace sestavení příkazového řádku.<br /><br /> Výchozí hodnota je "*NázevSpolečnosti ** název řešení solutionName* verze 1.0.", kde *#companyname* je název společnosti zadaný při instalaci systému Windows, a *název řešení solutionName*je název souboru řešení aplikace.|  
|DefaultDebugEngine|odkazy řetězců|Identifikátor GUID výchozí ladění modul použít pro aplikaci.<br /><br /> Poznámka: Prázdný identifikátor GUID (samými nulami) označuje, že aplikace neurčuje výchozí ladění modul. To umožňuje ladicího programu vyberte modul ladění používat.<br /><br /> Výchozí hodnota je "{00000000-0000-0000-0000-000000000000}".|  
|DefaultHomePage|odkazy řetězců|Výchozí domovská stránka adresa URL pro interní okno prohlížeče.<br /><br /> Pokud **domovskou stránku** možnost je dostupná v aplikaci a potom toto nastavení má vliv také výchozí stav možnost. Další informace najdete v tématu [webový prohlížeč, prostředí, dialogové okno Možnosti](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Výchozí hodnota je adresa URL společnosti zadaný při instalaci systému Windows.|  
|DefaultProjectsLocation|odkazy řetězců|Úplná cesta ke složce projekty výchozí. Například<br /><br /> `"DefaultProjectsLocation"="$MyDocuments$\MyVSShellStub\Projects"`<br /><br /> Pokud **umístění projektů sady Visual Studio** možnost je dostupná v aplikaci a potom toto nastavení má vliv také výchozí stav možnost. <br /><br /> Výchozí hodnota je "$MyDocuments$\\*název řešení solutionName*", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|DefaultSearchPage|odkazy řetězců|Výchozí URL stránky vyhledávání pro interní okno prohlížeče.<br /><br /> Pokud **stránky hledání** možnost je dostupná v aplikaci a potom toto nastavení má vliv také výchozí stav možnost. Další informace najdete v tématu [webový prohlížeč, prostředí, dialogové okno Možnosti](../ide/reference/web-browser-environment-options-dialog-box.md).<br /><br /> Výchozí hodnota je "http://search.live.com".|  
|DefaultUserFilesFolderRoot|odkazy řetězců|Název složky uživatele, vzhledem k aktuální uživatel je složka Dokumenty.<br /><br /> Výchozí hodnota je název souboru řešení aplikace.|  
|DisableOutputWindow|DWORD|Určuje, zda izolované prostředí by měly zpracovávat ve výstupním okně jako zakázané.<br /><br /> Pokud tato hodnota nastavena na hodnotu true, Visual Studio nezobrazuje výstupu manager sestavení řešení v **výstup** okno a skryje **okno zobrazit výstup při spuštění sestavení** zaškrtávací políčko  **Projekty a řešení** kategorie v **možnosti** dialogové okno.<br /><br /> Výchozí hodnota je False.|  
|HideMiscellaneousFilesByDefault|DWORD|Hodnotu PRAVDA, aby skrýt **různé soubory** složky ve výchozím nastavení v **Průzkumníku**, jinak hodnota false.<br /><br /> Pokud **zobrazit různé soubory v Průzkumníkovi řešení** možnost je dostupná v aplikaci a potom toto nastavení má vliv také výchozí stav možnost. Další informace najdete v tématu [dokumenty, prostředí, dialogové okno Možnosti](../ide/reference/documents-environment-options-dialog-box.md).<br /><br /> Výchozí hodnota je False.|  
|HideSolutionConcept|DWORD|Hodnota TRUE, má-li vytvořit všechny projekty jako samostatné projekty a řešení a související řešení příkazy pro samostatné projekty skrýt ve výchozím nastavení; jinak hodnota false.<br /><br /> Pokud **vždy zobrazovat řešení** možnost je dostupná v aplikaci a potom toto nastavení má vliv také výchozí stav možnost.<br /><br /> Výchozí hodnota je False.|  
|NewProjDlgInstalledTemplatesHdr|odkazy řetězců|Název hlavičky nstalled šablony sady Visual Studio v **šablony** v seznamu **nový projekt** dialogové okno. Toto je řetězec nebo identifikátor lokalizovatelný prostředku, který je načten z balíčku aplikace uživatelského rozhraní.<br /><br /> Výchozí hodnota je "*název řešení solutionName* – nainstalované šablony", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|NewProjDlgSlnTreeNodeTitle|odkazy řetězců|Název **řešení sady Visual Studio** uzel v **typy projektů** stromu v **nový projekt** dialogové okno. Toto je řetězec nebo identifikátor lokalizovatelný prostředku, který je načten z balíčku aplikace uživatelského rozhraní.<br /><br /> Výchozí hodnota je "*název řešení solutionName* – nainstalované šablony", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|SolutionFileCreatorIdentifier|odkazy řetězců|Identifikátor aplikace, která se zobrazí jako druhý řádek v souborech řešení, které jsou generovány aplikací. Tento řádek označuje aplikace, která vytvoří soubor. Podle konvence tato hodnota zahrnuje název aplikace a číslo verze aplikace. Například<br /><br /> `"SolutionFileCreatorIdentifier"="MyVSShellStub Solution File, Format Version 10.00"`<br /><br /> Program VSLauncher.exe, což je výchozí program pro otevření souboru řešení sady Visual Studio, používá tento druhý řádek k určení verze sady Visual Studio, ve kterém chcete otevřít soubor řešení. Aplikace by vyžadovaly vlastní Spouštěče zpracování souborů jeho přidružené řešení. Spouštěč může také použít tento druhý řádek v souboru řešení určit, ve kterou verzi aplikace pro otevření řešení.<br /><br /> Poznámka: Tento program Visual Studio VSLauncher.exe nezpracovává .sln soubory, které byly vytvořené pomocí aplikace izolované prostředí.<br /><br /> Výchozí hodnota je "*název řešení solutionName* soubor řešení, verze formátu 10,00", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|SolutionFileExt|odkazy řetězců|Přípona souboru řešení pro aplikaci. Doporučujeme, abyste zvolili rozšíření jedinečný název souboru (not.sln).<br /><br /> Výchozí hodnota je "*název řešení solutionName*_sln", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|SplashScreenBitmap|odkazy řetězců|Úplná cesta souboru bitové mapy pro úvodní obrazovky pro aplikaci.<br /><br /> Výchozí hodnota je "$RootFolder$\Splash.bmp".|  
|ThisVersionDTECLSID|odkazy řetězců|Identifikátor třídy (CLSID) objekt automatizace pro aplikaci.<br /><br /> Objekt automatizace aplikace je objekt nejvyšší úrovně pro aplikaci v sadě Visual Studio shell automatizace modelu a implementuje <xref:EnvDTE._DTE?displayProperty=fullName> rozhraní.<br /><br /> Pokud objekt automatizace aplikace je úspěšně zaregistrovaný v klíči registru HKEY_CLASSES_ROOT\CLSID, pak můžete použít [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) funkce, která se přímo vytvořit instanci aplikace.<br /><br /> Prostředí sady Visual Studio používá tento CLSID registrace objekt automatizace aplikace v spuštění objektu tabulky (kroužkovitosti) pomocí příznak ACTIVEOBJECT_WEAK. To vám umožní používat [getactiveobject –](http://msdn.microsoft.com/en-us/a276e30c-6a7f-4cde-9639-21a9f5170b62)funkce načíst ukazatel na běžící instanci aplikace. Kromě toho pokud definujete ProgID pro daný aplikační objekt automatizace, pak prostředí sady Visual Studio také zaregistruje každou instanci aplikace v kroužkovitosti pomocí zástupný název položky ve formátu *progID*:*ID procesu* , kde *progID* je identifikátor ProgID objekt automatizace aplikace a *processID* je identifikátor procesu pro tuto instanci aplikace. Například pokud vytvoříte Přezdívka následujícím způsobem:<br /><br /> `CreateItemMoniker(L"!",`  *instanceString*`, &instanceMoniker)`<br /><br /> kde `instanceString` je *progID*:*processID* řetězec. pak můžete použít `instanceMoniker` pomocí funkce ROT GetObject pro získání instance.<br /><br /> Pokud je vynechán ThisVersionDTECLSID nastavení, aplikace nebude vystavena prostřednictvím modelu COM (Component Object). V takovém případě nelze vytvořit instanci aplikace voláním [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) fungovat a nelze zaregistrovat ve kroužkovitosti.<br /><br /> Každá verze nástroje VSPackage musí mít jiný CLSID.<br /><br /> Výchozí hodnota je GUID, generovaný v sadě Visual Studio pro objekt automatizace aplikace.|  
|ThisVersionSolutionCLSID|odkazy řetězců|CLSID objekt řešení pro aplikaci.<br /><br /> Objekt řešení automatizace obsahuje informace o aktuálním otevřete řešení v instanci aplikace a implementuje <xref:EnvDTE._Solution?displayProperty=fullName> rozhraní.<br /><br /> Pokud je objekt automatizace řešení správně zaregistrován v klíči registru HKEY_CLASSES_ROOT\CLSID, pak můžete použít [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) funkce, která se přímo vytvářet objekt řešení pro aplikaci.<br /><br /> Prostředí sady Visual Studio používá tento CLSID zaregistrovat objekt automatizace řešení na kroužkovitosti pomocí příznaku ACTIVEOBJECT_WEAK.<br /><br /> Pokud toto nastavení je tento parametr vynechán, pak třída řešení není registrována s modelu COM (Component Object) a voláním nelze vytvořit objekt řešení [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance) funkce a nemůže být zaregistrován v KROUŽKOVITOSTI.<br /><br /> Výchozí hodnota je GUID generovaný pro objekt řešení aplikace Visual Studio.|  
|UserFilesSubFolderName|odkazy řetězců|Název podsložky ve složce Dokumenty uživatele, ve kterém aplikace vytvoří uživatelské soubory a podsložky.<br /><br /> Výchozí hodnota je název souboru řešení aplikace.|  
|UserOptsFileExt|odkazy řetězců|Rozšíření pro soubory možnosti uživatele řešení pro aplikaci.<br /><br /> Výchozí hodnota je název souboru řešení aplikace.|  
  
## <a name="binding-path-settings"></a>Nastavení cesty vazby  
 [$RootKey$ \BindingPaths\\{00000000-0000-0000-0000-000000000000}] klíč obsahuje seznam adresářů, které prostředí vyhledává sestavení. Tyto adresáře jsou přidány do seznamu adresáře, které testy prostředí pro soukromá sestavení pro aplikaci.  
  
 Ve výchozím nastavení jsou přidány žádné položky vazby cesta k souboru .pkgdef. Následující podadresářích adresáře instalace sady Visual Studio se automaticky přidají do seznamu aplikací vazby cesta v registru.  
  
-   Common7\IDE\  
  
-   Common7\IDE\\\PrivateAssemblies  
  
-   Common7\IDE\\\PublicAssemblies  
  
 Chcete-li přidat adresář do cesty vazby, přidejte položku ve tvaru "*directoryName*"="", kde *directoryName* je absolutní cesta. Například  
  
```  
[$RootKey$\BindingPaths\{00000000-0000-0000-0000-000000000000}]  
"$RootFolder$\directory1"=""  
"%CommonProgramFiles%\directory2"=""  
```  
  
## <a name="profile-settings"></a>Nastavení profilu  
 Následující tabulka popisuje hodnoty, které jsou definovány pro každý balíček přidružené pod [$RootKey$ \Profile].  
  
|Název|Typ|Hodnota|  
|----------|----------|-----------|  
|AutoSaveFile|odkazy řetězců|Adresář, ve kterém aplikace ukládá automatického ukládání souborů.<br /><br /> Výchozí hodnota je "$RootFolder$\Profiles\CurrentSettings.vssettings".|  
  
## <a name="package-satellite-dll-settings"></a>Nastavení balíčku satelitní knihovny DLL  
 Následující tabulka popisuje hodnoty, které jsou definovány v části [$RootKey$ \Packages\\{*vsPackageGuid*} \SatelliteDll] pro satelitní knihovny DLL jednotlivých přidružených balíčků, kde *vsPackageGuid* je identifikátor GUID přidruženého balíčku.  
  
|Název|Typ|Hodnota|  
|----------|----------|-----------|  
|DllName|odkazy řetězců|Název souboru knihovny DLL.<br /><br /> Výchozí hodnota je "*název řešení solutionName*ui.dll", kde *název řešení solutionName* je název souboru řešení aplikace.|  
|Cesta|odkazy řetězců|Adresář, který obsahuje satelitní knihovny DLL.<br /><br /> Výchozí hodnota je "$PackageFolder$".|  
  
## <a name="package-menu-item-settings"></a>Balíček nastavení položky nabídky  
 Klíče registru [$RootKey$ \Menus] definuje soubory prostředků uživatelského rozhraní pro aplikaci.  
  
 Hodnoty položek nabídky mají formuláře "{*vsUiPackageGuid*}"=", *resourceId*, *Cisloverze*", kde *vsUiPackageGuid* je identifikátor GUID balíček aplikace uživatelského rozhraní, *resourceId* je identifikátor prostředku CTMENU prostředku, který obsahuje prvky uživatelského rozhraní a *Cisloverze* je číslo virtuální verze pro CTMENU prostředek. Další informace najdete v tématu [registrace zprostředkovatele komunikace s objekty sestavení obslužné rutiny příkazů](../extensibility/internals/registering-interop-assembly-command-handlers.md).  
  
 Ve výchozím nastavení je záznam položky nabídky vytvořil v souboru .pkgdef balíčku aplikace uživatelského rozhraní.  
  
 Pro každý balíček, který obsahuje položky nabídky a který je distribuován jako součást aplikace přidejte položku nabídky položky pro balíček.  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení izolované prostředí](../extensibility/customizing-the-isolated-shell.md)   
 [. Pkgundef soubory](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgundef-file.md)