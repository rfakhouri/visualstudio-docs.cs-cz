---
title: "Stránka Možnosti, vlastnosti uzlu prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- automation [Visual Studio], controlling Tools Options
- Tools Options settings, Environment node properties
ms.assetid: 26dca41f-91fc-4ca7-9103-3da402baa1d5
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ae50f2d537836501ec4c9c29e50d86aa3e325661
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="options-page-environment-node-properties"></a>Stránka Možnosti, vlastnosti uzlu prostředí
Tento dokument popisuje stránky (nebo vlastnosti kolekce), jsou přidružené **prostředí** kategorie, `DTE.Properties("Environment", <Property Page>)`, z **možnosti** dialogové okno. Název každé část je hovoru, který se používá pro přístup ke kolekci vlastností a v tabulce v každou část jsou uvedeny vlastnosti v kolekci.  
  
## <a name="general"></a>Obecné  
 `DTE.Properties("Environment", "General")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|ShowStatusBar|Get/Set (Boolean)|Určuje, zda je viditelná stavový řádek.|  
|WindowMenuContainsNItems|Get/Set (krátký)|Určuje, jak windows dokumentu jsou obsaženy v dolní části nabídky systému Windows.|  
|MRUListContainsNItems|Get/Set (krátký)|Určuje, kolik souborů se zobrazí v podnabídce "Naposledy použitých".|  
|Animace|Get/Set (Boolean)|Určuje, zda integrované vývojové prostředí (IDE) používá animace ve stavovém řádku.|  
|AnimationSpeed|Get/Set (krátký)||  
|AutoAdjustExperience|Get/Set (Boolean)|Automaticky upraví visual prostředí v závislosti na výkonu klienta.|  
|RichClientExperienceOptions|Get/Set (Enum)|Umožňuje prostředí visual plně funkčního klienta s hodnotami ve <xref:EnvDTE100.vsRichClientExperienceOptions>.|  
|CloseButtonActiveTabOnly|Get/Set (Boolean)|Určuje, zda **Zavřít** tlačítko se zobrazí pouze na kartě aktivní.|  
|AutohidePinActiveTabOnly|Get/Set (Boolean)|Určuje, zda **automaticky skrýt** ovlivní pouze aktivní karty.|  
  
## <a name="add-inmacros-security"></a>Zabezpečení přidat v/makra  
 `DTE.Properties("Environment", "AddinMacrosSecurity")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|MacrosEnabled|Get/Set (Boolean)|Umožňuje spuštění maker.|  
|AddinsEnabled|Get/Set (Boolean)|Umožňuje doplňky načíst.|  
|LoadAddinsFromTheWeb|Get/Set (Boolean)|Umožňuje doplňky načíst z adresy URL na webu.|  
  
## <a name="documents"></a>Dokumenty  
 `DTE.Properties("Environment", "Documents")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|ReuseSavedActiveDocWindow|Get/Set (Boolean)|Určuje, jestli otevřete nový soubor opětovně používá aktuální okna dokumentu Pokud je uloženo aktuálním dokumentu. `false`znamená to vždy otevřete nové okno dokument pro každý dokument otevřít.|  
|DetectFileChangesOutsideIDE|Get/Set (Boolean)|Určuje, zda prostředí automaticky načte soubory otevřené v prostředí IDE, když se operační systém upozornění rozhraní IDE, že byl změněn soubory na disku.|  
|AutoloadExternalChanges|Get/Set (Boolean)|Určuje, zda zjistil, že externí úpravy otevírat dokumenty automaticky znovu načtěte změněný soubor Pokud otevřete dokument se nemění. Pokud se mění otevřít dokument a tato vlastnost je `true`, potom zobrazí výzvu rozhraní IDE, jako kdyby byla tato vlastnost `false`.|  
|InitializeOpenFileFromCurrentDocument|Get/Set (Boolean)|Určuje, zda <xref:EnvDTE.DTEClass.OpenFile%2A> příkaz doplňuje název adresáře a souboru z poslední aktivní dokument nebo v posledním místě můžete otevřít soubor.|  
|MiscFilesProjectSavesLastNItems|Get/Set (krátký)|Určuje, kolik souborů projektu záznamy různé soubory. V důsledku toho můžete zobrazit, co jste naposledy měl otevřete jako ostatní soubor na disku vedle pomocí rozhraní IDE.|  
|ShowMiscFilesProject|Get/Set (Boolean)|Určuje, zda je zobrazen různé soubory projektu.|  
|CheckForConsisentLineEndings|Get/Set (Boolean)|Kontroluje konzistentní konce řádků v souboru zatížení.|  
|SaveDocsAsUnicodeWhenDataLoss|Get/Set (Boolean)|Uloží dokumenty jako Unicode, když data nelze uložit v kódové stránky.|  
|DontShowGlobalUndoChangeLossDialog|Get/Set (Boolean)|Zobrazí upozornění, když se globální akci zpět upraví dalších upravených souborů.|  
|AllowEditingReadOnlyFiles|Get/Set (Boolean)|Umožňuje úpravy souborů jen pro čtení, ale udělení upozornění při pokusu o jejich uložení.|  
|DocumentDockPreference|Get/Set (Enum)|<xref:EnvDTE100.vsDocumentDockPreferenceOptions>. Pozice na kartě i v kterém se má vložit otevřenou dokumentu.|  
  
## <a name="extension-manager"></a>správce rozšíření  
 `DTE.Properties("Environment", "ExtensionManager")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|EnableAdminExtensions|Get/Set (Boolean)|Načte rozšíření na uživatele, když Visual Studio je spuštěná s pověřeními správce. Po změně této hodnoty je třeba restartovat Visual Studio.|  
|EnableOnline|Get/Set (Boolean)|Umožňuje přístup k rozšíření v Galerii Visual Studia.|  
|AutomaticallyCheckForUpdates|Get/Set (Boolean)|Automaticky zjišťuje aktualizace nainstalované rozšíření.|  
  
## <a name="find-and-replace"></a>hledání a nahrazování  
 `DTE.Properties("Environment", "FindAndReplace")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|ShowWarningMessages|Get/Set (Boolean)|Zobrazí upozorněních.|  
|InitializeFromEditor|Get/Set (Boolean)|Automaticky naplní **najít** pole s textem v editoru.|  
|ShowMessageBoxes|Get/Set (Boolean)|Zobrazí informační zprávy.|  
|HideWindowsAfterMatchFromQuickFindReplace|Get/Set (Boolean)|Skryje **najít a nahradit** okno po shody je vyhledán pomocí **rychlého hledání** nebo **rychle nahradit**.|  
  
## <a name="import-and-export-settings"></a>Import a Export nastavení  
 `DTE.Properties("Environment", "Import and Export Settings")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|TrackTeamSettings|Get/Set (Boolean)|Použije nastavení v souboru určeného TeamSettingsFile.|  
|TeamSettingsFile|Get/Set (String)|Název souboru, který má nastavení team.|  
|AutoSaveFile|Get/Set (String)|Název souboru, kde se automaticky uloží nastavení uživatele.|  
  
## <a name="international-settings"></a>Mezinárodní nastavení  
 `DTE.Properties("Environment", "International")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|Jazyk|Get/Set (String)|Hodnota LCID pro aktuální jazyk pro sadu Visual Studio.|  
  
## <a name="keyboard"></a>Klávesnice  
 `DTE.Properties("Environment", "Keyboard")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|Schéma|Get/Set (String)|Vrátí řetězec, který obsahuje integrované schéma, řetězec obsahující úplnou cestu .vsk souboru, který je načtena nebo "(výchozí)" Pokud žádný soubor .vsk je načtena.|  
  
## <a name="projects-and-solution"></a>Projekty a řešení  
 `DTE.Properties("Environment", "ProjectsAndSolution")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|OnRunOrPreview|Get/Set (String)|Určit, zda IDE všechno ukládat před zobrazení náhledu nebo spuštění integrovaný projektu.|  
|ProjectsLocation|Get/Set (String)|Určuje výchozí adresář kde **přidat projekt** dialogové okno uloží nové projekty.|  
|ShowOutputWindowBeforeBuild|Get/Set (Boolean)|Určuje, zda spuštění sestavení zobrazí **výstup** okno.|  
|ShowTaskListAfterBuild|Get/Set (Boolean)|Určuje, zda se zobrazí sestavení neúspěšné operace **seznam úkolů** po dokončení sestavení.|  
|TrackFileSelectionInExplorer|Get/Set (Boolean)|Určuje, zda je aktuální položky sledovány v **Průzkumníku řešení**.|  
|AlwaysShowSolutionNode|Get/Set (Boolean)|Určuje, zda je zobrazen uzel řešení.|  
|OnlySaveStartupProjectsAndDependencies|Get/Set (Boolean)|Určuje, zda operace ukládání jsou omezeny na projektů po spuštění a jejich závislé soubory.|  
|ShowAdvancedBuildConfigurations|Get/Set (Boolean)|Určuje, zda se zobrazí upřesněné konfigurace sestavení.|  
|ConcurrentBuilds|Get/Set (String)|Určuje maximální počet paralelní projektu sestavení, které se můžou vyskytnout.|  
|SaveNewProjects|Get/Set (Boolean)|Určuje, zda jsou po vytváří automaticky uloží nové projekty.|  
|PromptForRenameSymbol|Get/Set (Boolean)|Určuje, jestli vyžadovat symbolický přejmenování při přejmenování souborů.|  
|OnRunWhenErrors|Get/Set (Enum)|Určuje chování při spuštění při sestavení bylo dokončeno s chybami.|  
|OnRunWhenOutOfDate|Get/Set (Enum)|Určuje chování při spuštění, když na projekt je zastaralý.|  
|ProjectTemplatesLocation|Get/Set (String)|Adresář, který obsahuje šablony projektů uživatele.|  
|ProjectItemTemplatesLocation|Get/Set (String)|Adresář, který obsahuje šablony položek uživatele.|  
|DefaultBehaviorForStartupProjects|Get/Set (String)||  
|MSBuildOutputVerbosity|Get/Set (String)|Určuje úroveň podrobností pro sestavení výstupu.|  
  
## <a name="startup"></a>Spuštění  
 `DTE.Properties("Environment", "Startup")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|OnStartUp|Get/Set (Enum)|Akce se má provést při spuštění z <xref:EnvDTE.vsStartUp>, s hodnotami 0 až 5:<br /><br /> -0: Otevřete domovskou stránku<br />-1: zatížení posledního načtení řešení<br />-2: Zobrazit **otevřeného projektu** dialogové okno<br />-3: Zobrazit **nový projekt** dialogové okno<br />-4: zobrazit prázdný prostředí<br />-5: zobrazit úvodní stránku|  
|StartPageRSSUrl|Get/Set (String)|Adresa URL pro kanálu RSS, který se používá při spuštění.|  
|StartPageRefreshDownloadedContent|Get/Set (Boolean)|Aktualizuje stránku spustit po každé průchodu intervalu zadaném ve StartPageRefreshInterval.|  
|StartPageRefreshInterval|Get/Set (krátký)|Interval v minutách obnovíte stránku spustit.|  
  
## <a name="tasklist"></a>TaskList  
 `DTE.Properties("Environment", "TaskList")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|ConfirmTaskDeletion|Get/Set (Boolean)|Určuje, zda potvrzovací okno se zobrazí, když se odstranění úlohy z **seznam úkolů**.|  
|WarnOnAddingHiddenItem|Get/Set (Boolean)|Určuje, zda budete varováni při přidávání uživatele úlohu, která se nezobrazí.|  
|DontShowFilePaths|Get/Set (Boolean)|Určuje, jestli zobrazíte úplné cesty v seznamu úkolů.|  
|CommentTokens|SafeArray|Vrátí SafeArray komentáře hodnoty tokenu. Každá z nich má pole, `Name` (string) a `Priority` (<xref:EnvDTE.vsTaskPriority>, vysoká, střední nebo nízká).|  
  
## <a name="web-browser"></a>Webový prohlížeč  
 `DTE.Properties("Environment", "WebBrowser")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|Domovská stránka|Get/Set (String)|Představuje adresu URL domovské stránky.|  
|SearchPage|Get/Set (String)|Představuje adresu URL stránky vyhledávání.|  
|ViewSourceIn|Get/Set (Enum)|<xref:EnvDTE.vsBrowserViewSource>(Externí zdroj, návrh,).|  
|ViewSourceExternalProgram|Get/Set (String)|Cesta v prohlížeči externího zdroje.|  
  
## <a name="see-also"></a>Viz také  
 [Ovládání možnosti nastavení](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Určení názvů vlastností položky na stránkách možnosti](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Stránka Možnosti, písma a barvy vlastnosti uzlu](../../ide/reference/options-page-fonts-and-colors-node-properties.md)   
 [Stránka Možnosti, vlastnosti uzlu textového editoru](../../ide/reference/options-page-text-editor-node-properties.md)   
 [Dialogové okno Možnosti prostředí](../../ide/reference/environment-options-dialog-box.md)