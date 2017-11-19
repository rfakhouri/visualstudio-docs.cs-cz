---
title: "Projekt modelu základní součásti služby | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project models, objects and interfaces
- project models, services
ms.assetid: b2f572d3-b26d-4846-92d1-84055fac141a
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c7759a2394f2cda19f875a85a22c4a674fee8964
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="project-model-core-components"></a>Základní součásti služby projektu modelu
V následujících tabulkách rozbalit na projekt modelu. Stručný popis rozhraní a služeb, které jsou určené v modelu a rozhraní a služby se specifickými objekty přidružené k dispozici v tabulkách. Kromě toho tabulky Podrobnosti dalších rozhraní, které jsou volitelné při vytváření projektu a údržbě v závislosti na požadavcích vaší konkrétní projekt typu.  
  
 Další informace najdete v tématu [procházení podpora Symbol nástroje](../../extensibility/internals/supporting-symbol-browsing-tools.md).  
  
### <a name="package-object"></a>Objekt balíček  
  
|Rozhraní|Komentáře|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>|Inicializuje VSPackage v prostředí IDE a zpřístupní její služby k prostředí IDE.|  
  
### <a name="project-factory-object"></a>Objekt Factory projektu  
  
|Rozhraní|Komentáře|  
|---------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|Spravuje vytváření nových projektů a otevření stávajících projektů.|  
  
### <a name="project-objects"></a>Objekty projektu  
  
|Rozhraní|Komentáře|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3>|Spravuje přidávání a odebírání položek projektu, který otevře editory a udržuje mapování mezi Přezdívka každý dokument a `VSITEMID`. Dědí z `IVsProject` a `IVsProject2`.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|Spravuje vlastnosti navigace a zobrazení a poskytuje události.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>|Příkaz povoluje provádění podobná `IOleCommandTarget` pro příkazy jako vyjmutí a přejmenování, které platí, pouze když je zaměřena v Průzkumníku řešení.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|Slouží jako cílové rozhraní primární příkazu hierarchii. Jedná se o standardní rozhraní pro dotazování objekty pro jejich příkaz stavu nebo stavu a spouštění příkazů. Tato možnost je k dispozici, pokud nejsou zaměřené v okně projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat>|Koordinuje trvalost stavu projektu. Obvykle stavu projektu je uložený jako soubor projektu, ale dokáže se přizpůsobit úložných systémů, které nejsou založené na souborech.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2>|Umožňuje projektu ke správě všech aspektů zachování jeho položky projektu, buď jako soubory na disku, nebo objekty v jiných systémů úložiště. `IVsPeristHierarchyItem2` Rozhraní se používá pro položky, které neimplementují <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistDocData2> rozhraní.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Koordinuje interakce s zdrojového kódu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFlavorCfgProvider>|Umožňuje projektů se mají spravovat informace o konfiguraci.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>|Spravuje objekty konfigurace projektu, jako je například konfigurace ladění a verze. Sestavení, nasazení a ladění operace jsou koordinované prostřednictvím objektů konfigurace projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDeleteHandler>|Implementované hierarchií řízení odstranění (destruktivní) nebo odebrat (bez destruktivní) možnosti pro položky v hierarchii. Volání rozhraní dotaz na `IVsHierarchyDeleteHandler` rozhraní z `IVsHierarchy` rozhraní.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsGetCfgProvider>|Poskytuje možnost implementace toho, že objekt, který podporuje `IVsCfgProvider2` rozhraní na jinou identitu COM než projektu objektu, který implementuje `IVsHierarchy` rozhraní.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectStartupServices>|Volitelné rozhraní implementované jinými vývojáři aby extensible projektu. `IVsProjectStartupServices` Rozhraní umožňuje VSPackage třetích stran k registraci identifikátor GUID, který zachovat v souboru projektu, aby pokaždé, když načtení projektu do souboru projektu a volání načíst službu třetí strany GUID `QueryService` pro tento identifikátor GUID.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelperEvents>|Implementované v zdrojových hierarchií `UIHierarchy` okno koordinaci schránky operací, jako je vyjmutí, kopírování a vložení. Použití `AdviseClipboardHelperEvents` rozhraní zaregistrovat schránku události.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataSource2>|Poskytuje informace o taženou položku relativně ke zdroji dat během operace přetažení myší v okně hierarchie uživatelského rozhraní. Volání z `IVsHierarchy` rozhraní.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchyDropDataTarget>|Poskytuje informace o taženou položku relativně k jeho cíle přetažení během operace přetažení myší v okně hierarchie uživatelského rozhraní. Volání z `IVsHierarchy` rozhraní.|  
  
### <a name="configuration-object"></a>Objekt konfigurace  
  
|Rozhraní|Komentáře|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg>|Poskytuje informace o konfiguraci.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>|Umožňuje projektů se mají spravovat informace o konfiguraci.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|Umožňuje projekt, který má být spuštěn pod kontrolou ladicího programu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg>|Implementované projekty nasazení, které provádí operace nasazení pro další projekty.|  
  
### <a name="configuration-builder-object"></a>Objekt konfigurace Tvůrce  
  
|Rozhraní|Komentáře|  
|----------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg>|Spravuje operace sestavení konfigurací projektu.|  
  
### <a name="additional-project-objects"></a>Další objekty projektu  
  
|Rozhraní|Komentáře|  
|----------------|--------------|  
|`IDispatch`<br /><br /> <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages>|Zobrazí položky vlastnosti v **vlastnosti** okno.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs>|Zobrazí výstupy pro nasazení.|  
  
 Následující tabulka obsahuje stručný popis služeb stanovených ve model projektu.  
  
### <a name="services"></a>Služby  
  
|Služba|Komentáře|  
|-------------|--------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|Používá VSPackages, které implementují typy projektů k registraci, existuje jejich objekt pro vytváření projektu pomocí rozhraní IDE. Vaše VSPackage musí volat `QueryService` pro tuto službu a zaregistrujte jeho vytváření projektu při `IVsPackage::SetSite` metoda je volána. Pokud `SetSite` metoda není volána, není vytvořena instance projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|Poskytuje přístup k rozhraní IDE interní, integrované představu o aktuální řešení, například možnost výčet projekty, vytvořte nové projekty, vzít v úvahu změny projektu a tak dále.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|Voláno rozhraním projekty, které se chcete zapojit se do správy zdrojového kódu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|Udržuje tabulku otevřené dokumenty k určení, zda jeden nebo více položek vašeho projektu je již otevřen.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|Obsahuje rozhraní a metody názvem projektu položku pomocí editoru standardní nebo konkrétní editoru otevřete ve skutečnosti.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|Abyste mohli volat všechny projekty, pokud se přidat, odebrat nebo přejmenovat své položky.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|Spravuje změny pro soubor nebo adresář a upozorní klientům, když se změnily vybrané soubory na disku.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|Abyste mohli volat všechny projekty a editory před jejich nesprávné položky nebo je uložíte.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|Spravuje pořadí operace sestavení a nasazení pro konfigurace projektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|Poskytuje přístup ke službám nízké úrovně ladicí program používá pro většinu ladění ovládacích prvků.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|Umožňuje VSPackages přístup k informacím o aktuální výběr a umožňuje komunikaci se **vlastnosti** okno.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|Poskytuje základní funkce související s uživatelského rozhraní IDE, jako je například možnost vytvoření a zobrazení výčtu nástroj windows nebo windows dokumentu nebo tak, aby odesílaly chybu uživatele.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|Poskytuje přístup k rozhraní IDE stavový řádek.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExtensibility3>|Slouží k implementaci automatizace modelu. V projektu modelu, vrátíte se na objekt vlastnosti, které vám umožní vytvoří instanci tohoto objektu.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|Slouží k implementaci schránky události v projektu objektu v hierarchii. `SVsUIHierWinClipboardHelper`umožňuje správně popisovač vyjmutí, kopírování a vložení operace.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>   
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Není v sestavení: použití HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [Podpůrné nástroje procházení – Symbol](../../extensibility/internals/supporting-symbol-browsing-tools.md)   
 [Prvky modelu projektu](../../extensibility/internals/elements-of-a-project-model.md)