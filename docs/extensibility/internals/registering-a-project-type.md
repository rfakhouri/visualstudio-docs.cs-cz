---
title: Registrace typu projektu | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], new project registry entries
- registry, new project types
- registration, new project types
ms.assetid: dfc0e231-6b4e-447d-9d64-0e66dea3394a
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: f60cf3fc8b4db7d33523e4583ab3da4f4596b1af
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="registering-a-project-type"></a>Registrace typu projektu
Když vytvoříte nový typ projektu, musíte vytvořit položky registru, které umožňují [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] rozpoznat a pracovat s typ vašeho projektu. Obvykle vytvoříte tyto položky registru pomocí souboru registru skript (.).  
  
 V následujícím příkladu příkazy z registru zadejte výchozí cesty a data případně následuje tabulku, která obsahuje položky z registru skript pro každý příkaz. V tabulkách položkami skriptu a další informace o dotazech.  
  
> [!NOTE]
>  Do registru následující informace slouží jako příklad typu a účely položky v registru skripty, které vytváříte, používáte k registraci typu vašeho projektu. Skutečné položky a jejich použití mohou lišit podle specifických požadavků vašeho projektu typu. Zkontrolujte vzorků, které jsou k dispozici pro nenajde, který se velmi podobá typu projektu, které vyvíjíte a pak zkontrolujte skript registru pro tuto ukázku.  
  
 Následující příklady jsou z HKEY_CLASSES_ROOT.  
  
## <a name="example"></a>Příklad  
  
```  
\.figp  
   @="FigPrjFile"  
   "Content Type"="text/plain"  
\.figp\ShellNew  
   "NullFile"=""  
\FigPrjFile  
   @="Figure Project File"  
\DefaultIcon  
   @="<Visual Studio SDK installation path>\\9.0VSIntegration\\SomeFolder\\FigPkgs\\FigPrj\\Debug\\FigPrj.dll,-206"  
\shell\open  
   @="&Open in Visual Studio"  
\shell\open\command  
   @="devenv.exe \"%1\""  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`FigPrjFile`|Název a popis projektu zadejte soubory, které mají .figp rozšíření.|  
|`Content Type`|REG_SZ|`Text/plain`|Typ obsahu pro soubory projektu.|  
|`NullFile`|REG_SZ|`Null`||  
|`@`|REG_SZ|`%MODULE%,-206`|Výchozí ikona použitá pro projekt tohoto typu. Příkaz % % modulu byla dokončena v registru na výchozí umístění typ projektu knihovny DLL.|  
|`@`|REG_SZ|`&Open in Visual Studio`|Výchozí aplikace, ve kterém se tento typ projektu otevřen.|  
|`@`|REG_SZ|`devenv.exe "%1"`|Výchozí příkaz, který se má spustit při otevření projektu tohoto typu.|  
  
 Následující příklady jsou z HKEY_LOCAL_MACHINE a jsou umístěny v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\99.0Exp\Packages].  
  
## <a name="example"></a>Příklad  
  
```  
\{ACEF4EB2-57CF-11D2-96F4-000000000000} (The CLSID for the VSPackage)  
   @="FigPrj Project Package"  
   "InprocServer32"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\                      Debug\\FigPrj.dll"  
   "CompanyName"="Microsoft"  
   "ProductName"="Figure Project Sample"  
   "ProductVersion"="9.0"  
   "MinEdition"="professional"  
   "ID"=dword:00000001  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\SatelliteDLL  
   "DllName"="FigPrjUI.dll"  
   "Path"="9.0<Visual Studio SDK installation path>\\VSIntegration\\Archive\\FigPkgs\\FigPrj\\Debug\\"  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\Automation  
   "FigProjects"=""  
\{ACEF4EB2-57CF-11D2-96F4-000000000000}\AutomationEvents  
   "FigProjectsEvents"="Returns the FigProjectsEvents Object"  
   "FigProjectItemsEvents"="Returns the FigProjectItemsEvents Object"  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`(Výchozí)|REG_SZ|`FigPrj Project VSPackage`|Lokalizovatelný název tohoto zaregistrovat VSPackage (typ projektu).|  
|`InprocServer32`|REG_SZ|`%MODULE%`|Cesta typu projektu knihovny DLL. Prostředí IDE načte této knihovny DLL a předá CLSID VSPackage k `DllGetClassObject` získat <xref:Microsoft.VisualStudio.OLE.Interop.IClassFactory> vytvořit <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> objektu.|  
|`CompanyName`|REG_SZ|`Microsoft`|Název společnosti, který vyvinul typ projektu.|  
|`ProductName`|REG_SZ|`Figure Project Sample`|Název pro typ projektu.|  
|`ProductVersion`|REG_SZ|`9.0`|Číslo verze typ projektu verzi.|  
|`MinEdition`|REG_SZ|`professional`|Edice VSPackage registrována.|  
|`ID`|REG_DWORD|`%IDS_PACKAGE_LOAD_KEY%`|Balíček načíst klíč pro projekt VSPackage. Klíč je ověřeno při načtení projektu po spuštění prostředí.|  
|`DllName`|REG_SZ|`%RESOURCE_DLL%`|Název souboru satelitní knihovny DLL, která obsahuje lokalizované prostředky pro typ projektu.|  
|`Path`|REG_SZ|`%RESOURCE_PATH%`|Cesta satelitní knihovny DLL.|  
|`FigProjectsEvents`|REG_SZ|Naleznete v prohlášení pro hodnotu.|Určuje textový řetězec, který vrátil pro tuto událost automatizace.|  
|`FigProjectItemsEvents`|REG_SZ|Naleznete v prohlášení pro hodnotu.|Určuje textový řetězec, který vrátil pro tuto událost automatizace.|  
  
 V následujících příkladech jsou umístěny v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects].  
  
## <a name="example"></a>Příklad  
  
```  
\{C061DB26-5833-11D2-96F5-000000000000} (The CLSID for projects of this type)  
   @="FigPrj Project"  
   "DisplayName"="#2"  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "ProjectTemplatesDir"="C:\\Program Files\\VSIP 9.0\\EnvSDK\\FigPkgs\\                           FigPrj\\FigPrjProjects"  
   "ItemTemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                           FigPrjProjectItems"  
   "DisplayProjectFileExtensions"="#3"  
   "PossibleProjectExtensions"="figp"  
   "DefaultProjectExtension"=".figp"  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\1       (Folder 1 contains settings for Open Files filters.)  
   @="#4"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000000  
   "FindInFilesFilter"=dword:00000000  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\Filters\2  
      (Folder 2 contains settings for Find in Files filters.)  
   @="#5"  
   "CommonOpenFilesFilter"=dword:00000000  
   "CommonFindFilesFilter"=dword:00000000  
   "NotAddExistingItemFilter"=dword:00000001  
   "FindInFilesFilter"=dword:00000001  
   "NotOpenFileFilter"=dword:00000000  
   "SortPriority"=dword:000003e8  
\{C061DB26-5833-11D2-96F5-000000000000}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (Second GUID indicates the registered project type for the Add Items templates.)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`FigPrj Project`|Výchozí název projekty tohoto typu.|  
|`DisplayName`|REG_SZ|`#%IDS_PROJECT_TYPE%`|ID prostředku názvu mají být načteny z satelitní knihovny DLL je registrovaná pod balíčky.|  
|`Package`|REG_SZ|`%CLSID_Package%`|ID třídy VSPackage zaregistrovaný pod balíčky.|  
|`ProjectTemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Výchozí cesta šablona projektu souborů. Jsou to soubory nový projekt šablonou zobrazena.|  
|`ItemTemplatesDir`|REG_SZ|`%TEMPLATE_PATH% \FigPrjProjectItems`|Výchozí cesta soubory šablony položek projektu. Jsou to soubory zobrazí šablony přidat novou položku.|  
|`DisplayProjectFileExtensions`|REG_SZ|`#%IDS_DISPLAY_PROJ_FILE_EXT%`|Umožňuje IDE implementovat **otevřete** dialogové okno.|  
|`PossibleProjectExtensions`|REG_SZ|`figp`|Prostředí IDE používá k určení, zda se otevření projektu používá tento typ projektu (factory projektu). Formát pro více než jedna položka je seznam oddělený středníky. Například "vdproj; vdp".|  
|`DefaultProjectExtension`|REG_SZ|`.figp`|Pomocí rozhraní IDE použít jako výchozí příponu názvu souboru pro operaci uložit jako.|  
|`Filter Settings`|REG_DWORD|Zobrazit různé, příkazy a komentáře následující tabulka.|Toto nastavení slouží k nastavení pro různé filtry pro zobrazení souborů v dialogových oknech uživatelského rozhraní.|  
|`@`|REG_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|ID prostředku pro šablony přidat položku.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|Cesta položky projektu zobrazí v dialogovém okně pro **přidat novou položku** šablony.|  
|`SortPriority`|REG_DWORD|`100 (vcprx64)`|Určuje pořadí řazení v uzlu stromu souborů v zobrazí **přidat novou položku** dialogové okno.|  
  
 V následující tabulce jsou filtry možnosti dostupné v předchozí segment kódu.  
  
|Možnost Filter|Popis|  
|-------------------|-----------------|  
|`CommonFindFilesFilter`|Označuje, že filtr je jednou z běžných filtry v **hledání v souborech** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|  
|`CommonOpenFilesFilter`|Označuje, že filtr je jednou z běžných filtry v **otevření souboru** dialogové okno. Běžné filtry jsou uvedeny v seznamu filtru před filtry, které nejsou označeny jako běžné.|  
|`FindInFilesFilter`|Označuje, že filtr bude jeden z filtrů v **hledání v souborech** dialogové okno pole a objeví se po běžné filtry.|  
|`NotOpenFileFilter`|Označuje, že filtr nebude použita v **otevření souboru** dialogové okno.|  
|`NotAddExistingItemFilter`|Označuje, že filtr nebude použita v přidáním **existující položka** dialogové okno.|  
  
 Ve výchozím nastavení, pokud filtr nemá jeden nebo více z těchto příznaků sady filtr se používá v **přidat existující položku** dialogové okno a **otevření souboru** dialogové okno po jsou uvedeny běžné filtry. Filtr se nepoužívá v **hledání v souborech** dialogové okno.  
  
 V následujících příkladech jsou umístěny v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects].  
  
## <a name="example"></a>Příklad  
  
```  
{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4} (The CLSID for Enterprise Projects)  
\{FE3BBBB6-72D5-11d2-9ACE-00C04F79A2A4}\AddItemTemplates\TemplateDirs\ {ACEF4EB2-57CF-11D2-96F4-000000000000}\1 (CLSID for projects of this type)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`#%IDS_NEWPROJ_ TEMPLATES_ENTRY%`|ID prostředku pro nový projekt šablony.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Výchozí cesta pro projekty typu registrované projektu.|  
|`SortPriority`|REG_DWORD|`41 (x29)`|Nastaví pořadí projekty, na které se zobrazí v dialogovém okně nové projekty průvodce řazení.|  
|`NewProjectDialogOnly`|REG_DWORD|`0`|Hodnota 0 znamená, že projekty tohoto typu se zobrazují pouze v dialogovém okně Nový projekt.|  
  
 V následujících příkladech jsou umístěny v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Projects].  
  
## <a name="example"></a>Příklad  
  
```  
\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3} (CLSID for Miscellaneous Files projects)  
   @="Miscellaneous Files Project"  
\AddItemTemplates\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1  
                                 (CLSID for Figures Project projects)  
   @="#6"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\                    FigPrjProjectItems"  
   "SortPriority"=dword:00000064  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|Žádné|Výchozí hodnota, která udává, že následující položky pro ostatní soubory položek projektů.|  
|`@`|REG_SZ|`#%IDS_ADDITEM_TEMPLATES_ENTRY%`|Hodnota ID prostředku pro soubory šablon přidat nové položky.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjectItems`|Výchozí cesta položek, které se zobrazí na **přidat novou položku** dialogové okno.|  
|`SortPriority`|REG_DWORD|`100 (vcprx64)`|Určuje pořadí řazení pro zobrazení v uzlu stromu **přidat novou položku** dialogové okno.|  
  
 V následujícím příkladu se nachází v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\Menus].  
  
## <a name="example"></a>Příklad  
  
```  
"{ACEF4EB2-57CF-11D2-96F4-000000000000}"=",1000,1"  
```  
  
 Položka nabídky odkazuje na prostředek, který používá načíst informace o nabídce rozhraní IDE. Pokud tato data byla sloučena do nabídky databáze, přidá se stejným klíčem v části MenusMerged registru. VSPackage nesmí upravovat nic části MenusMerged přímo. V datovém poli v následující tabulce jsou tři čárkami oddělené pole. První pole určuje úplnou cestu souboru prostředků nabídky:  
  
-   Pokud je vynechán první pole, je ze satelitní knihovny DLL identifikovanou pomocí identifikátoru GUID VSPackage načíst prostředků nabídky.  
  
 Druhé pole identifikuje ID prostředku nabídky typu CTMENU:  
  
-   Pokud je zadané ID prostředku a cesta k souboru poskytl první parametr, nabídky prostředků je načten z úplnou cestou k souboru.  
  
-   Pokud je zadané ID prostředku, ale není cesta k souboru, prostředků nabídky je načten z satelitní knihovny DLL.  
  
-   Pokud je k dispozici je úplná cesta a ID prostředku tento parametr vynechán, musí být soubor technického ředitele načtení souboru.  
  
 Poslední pole identifikuje číslo verze pro prostředek CTMENU. V nabídce můžete sloučit znovu změnou číslo verze.  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|% CLSID_Package %|REG_SZ|`,1000,1`|Prostředek se načíst informace o nabídce.|  
  
 V následujících příkladech jsou umístěny v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\NewProjectTemplates].  
  
```  
\TemplateDirs\{ACEF4EB2-57CF-11D2-96F4-000000000000}\1                (CLSID for Figures Project projects)  
   @="#7"  
   "TemplatesDir"="<Visual Studio SDK installation path>\\VSIntegration\\Archive9.0\\FigPkgs\\FigPrj\\FigPrjProjects"  
   "SortPriority"=dword:00000029  
   "NewProjectDialogOnly"=dword:00000000  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`@`|REG_SZ|`#%IDS_NEWPROJ_TEMPLATES_ENTRY%`|Hodnota ID prostředku pro obrázky projektu nový projekt šablony.|  
|`TemplatesDir`|REG_SZ|`%TEMPLATE_PATH%\FigPrjProjects`|Výchozí cesta adresáře nové projekty. Položky v tomto adresáři se zobrazí na **Průvodce nový projekt** dialogové okno.|  
|`SortPriority`|REG_DWORD|`41 (x29)`|Určuje pořadí, ve kterém se zobrazí projekty v uzlu stromu **nový projekt** dialogové okno.|  
|`NewProjectDialogOnly`|REG_DWORD|`0`|0 znamená, že projekty tohoto typu se zobrazují pouze v **nový projekt** dialogové okno.|  
  
 V následujícím příkladu se nachází v registru pod klíčem [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0Exp\InstalledProducts].  
  
```  
\FiguresProductSample  
   "Package"="{ACEF4EB2-57CF-11D2-96F4-000000000000}"  
   "UseInterface"=dword:00000001  
```  
  
|Název|Typ|Data|Popis|  
|----------|----------|----------|-----------------|  
|`Package`|REG_SZ|`%CLSID_Package%`|ID třídy registrované VSPackage.|  
|`UseInterface`|REG_DWORD|`1`|1 znamená, že bude použit uživatelského rozhraní pro interakci s Tento projekt. 0 znamená, že existuje bez uživatelského rozhraní.|  
  
 The.vsz soubory, které často řídí nové typy projektů obsahovat položku RELATIVE_PATH. Tato cesta je relativní vzhledem ke zadaná pod položkou \ProductDir projektu typu v následujícím klíči Instalační cesta:  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\7.0Exp\Setup  
  
 Šablony projektů architektury Enterprise například přidat následující položky registru:  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\7.0Exp\Setup\EF\ProductDir = C:\Program Files\Microsoft Visual Studio\EnterpriseFrameworks\  
  
 To znamená, že pokud zahrnete PROJECT_TYPE = EF záznam v souboru najde prostředí vaší .vsz soubory v adresáři ProductDir zadali dřív.  
  
## <a name="see-also"></a>Viz také  
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)   
 [Vytváření instancí projektu pomocí objektů pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)