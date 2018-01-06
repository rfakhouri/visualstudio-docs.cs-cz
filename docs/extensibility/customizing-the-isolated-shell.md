---
redirect_url: shell/customizing-the-isolated-shell
title: "Přizpůsobení izolované prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: e0b7c3ae-210f-4f48-ac49-6a59e6034f5f
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e02d93e966f676e0933b866cc8e74bfdd011231f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="customizing-the-isolated-shell"></a>Přizpůsobení izolované prostředí
Aplikace Visual Studio izolované prostředí můžete přizpůsobit tak, že změníte různé aspekty uživatelského rozhraní sady Visual Studio a omezení příkazy a funkce obsažené v aplikaci speciální.  
  
## <a name="using-the-applicationpkgdef-file"></a>Pomocí souboru Application.pkgdef  
 Izolované prostředí šablony řešení zahrnuje *název řešení SolutionName*. Application.pkgdef soubor, který vám umožní změnit následující funkce:  
  
##### <a name="the-application-title"></a>Název aplikace  
 Můžete přizpůsobit název aplikace, který je název, který se zobrazí v záhlaví aplikace, můžete změnit hodnotu v řádku "AppName" *název řešení SolutionName*. Application.pkgdef soubor. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
 Pokud nechcete, aby název aplikace, které chcete zobrazit projekt, který je aktuálně načtený, změňte hodnotu v řádku "ShowHierarchyRootInTitle" *název řešení SolutionName*. Application.pkgdef soubor z DWORD: 00000001 DWORD: 00000000.  
  
##### <a name="the-application-icon"></a>Ikona aplikace  
 Ikona aplikace, což je ikona, která se zobrazí název aplikace v záhlaví aplikace můžete přizpůsobit. Vlastní ikonu zkopírujte do adresáře ikonu. V **Průzkumníku**, přidejte na ikonu do složky, soubory prostředků. Potom otevřete soubor VSShellStub.rc a nahraďte hodnotu IDI_STUBPROGRAM s názvem na ikonu nový. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-command-line-logo"></a>Logo příkazového řádku  
 Můžete přizpůsobit logo příkazového řádku, což je text, který se zobrazí, když je aplikace spuštěna z příkazového řádku, můžete změnit hodnotu v řádku "CommandLineLogo" *název řešení SolutionName*. Application.pkgdef soubor. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="the-name-of-the-user-files-subfolder"></a>Název podsložky soubory uživatele  
 Můžete změnit název složky aplikace udržuje pro uživatele soubory změnou hodnoty v řádku "UserFilesSubFolderName" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-title-of-the-solution-tree-node-in-the-new-project-dialog"></a>Název uzlu stromu řešení v dialogovém okně Nový projekt  
 Název uzlu řešení v dialogovém okně Nový projekt můžete upravit změnou hodnoty v řádku "NewProjDlgSlnTreeNodeTitle" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-installed-templates-header-in-the-new-project-dialog"></a>Hlavička nainstalovaných šablon v dialogu Nový projekt  
 Hlavička nainstalovaných šablon v dialogu Nový projekt můžete změnit změnou hodnoty v řádku "NewProjDlgInstalledTemplatesHdr" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="whether-or-not-to-hide-miscellaneous-files-by-default"></a>Zda chcete skrýt ostatní soubory ve výchozím nastavení  
 Můžete zadat, zda chcete skrýt ostatní soubory ve výchozím nastavení můžete změnit hodnotu v řádku "HideMiscellaneousFilesByDefault" *název řešení SolutionName*. Application.pkgdef soubor. Chcete-li skrýt ostatní soubory, nastavte hodnotu `dword:00000001`a pokud chcete zobrazit soubory, nastavte hodnotu `dword:00000000`.  
  
##### <a name="whether-or-not-to-disable-the-output-window"></a>Zda chcete zakázat ve výstupním okně  
 Můžete zadat, zda chcete zakázat změnou hodnoty řádku "DisableOutputWindow" v okně výstupu v aplikaci *název řešení SolutionName*. Application.pkgdef soubor. Chcete-li zakázat ve výstupním okně, nastavte hodnotu `dword:00000001`a pokud chcete zobrazit ve výstupním okně, nastavte hodnotu `dword:00000000`.  
  
##### <a name="whether-or-not-to-allow-dropped-files-on-the-main-window"></a>Zda se má povolit vynechaných soubory v hlavním okně  
 Můžete zadat, zda se má povolit vynechaných souborů v hlavním okně ve vaší aplikaci změnou hodnoty v řádku "AllowsDroppedFilesOnMainWindow" *název řešení SolutionName*. Application.pkgdef soubor. Chcete-li povolit vynechaných soubory, nastavte hodnotu `dword:00000001`a tak, aby zakázala vynechaných soubory, nastavte hodnotu `dword:00000000`.  
  
##### <a name="the-default-search-page"></a>Výchozí stránka vyhledávání  
 Můžete přizpůsobit stránka webového prohlížeče, které je stránka, která se zobrazí po otevření okna prohlížeče, změnou hodnoty v řádku "DefaultSearchPage" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-default-home-page"></a>Výchozí domovskou stránku  
 Na domovskou stránku můžete přizpůsobit změnou hodnoty v řádku "DefaultHomePage" *název řešení SolutionName*. Application.pkgdef soubor. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="whether-or-not-to-hide-the-solution-concept"></a>Zda chcete skrýt koncept řešení  
 Můžete zadat, zda chcete skrýt řešení ve vaší aplikaci změnou hodnoty v řádku "HideSolutionConcept" *název řešení SolutionName*. Application.pkgdef soubor. Chcete-li skrýt řešení, nastavte hodnotu `dword:00000001`a chcete-li zobrazit řešení, nastavte hodnotu `dword:00000000`.  
  
##### <a name="the-default-debug-engine"></a>Výchozí modul ladění  
 Modul ladění vaše aplikace používá změnou hodnoty v řádku "DefaultDebugEngine", můžete změnit *název řešení SolutionName*. Soubor Application.pkgdef na identifikátor GUID modul ladění.  
  
##### <a name="the-file-extension-of-the-user-options-file"></a>Přípona souboru soubor možnosti uživatele  
 Můžete změnit název složky aplikace udržuje pro uživatele soubory změnou hodnoty v řádku "UserOptsFileExt" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-solution-file-extension"></a>Přípona souboru řešení  
 Můžete změnit rozšíření používané pro vaše řešení soubory změnou hodnoty v řádku "SolutionFileExt" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-default-user-files-folder-root"></a>Kořenové složky výchozí uživatelské soubory  
 Název kořenové složky soubory uživatele pro vaši aplikaci můžete změnit změnou hodnoty v řádku "UserFilesSubFolderName" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-solution-file-creator-identifier"></a>Identifikátor creator soubor řešení  
 Identifikátor použitý pro vaše řešení soubory změnou hodnoty v řádku "SolutionFileCreatorIdentifier", můžete změnit *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-default-projects-location"></a>Výchozí umístění projekty  
 Název výchozí umístění projekty můžete změnit změnou hodnoty v řádku "DefaultProjectsLocation" *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="the-application-localization-package"></a>Lokalizace balíček aplikace  
 Lokalizace balíčku pro aplikace změnou hodnoty v řádku "AppLocalizationPackage", můžete změnit *název řešení SolutionName*. Application.pkgdef soubor.  
  
##### <a name="whether-or-not-to-show-the-hierarchy-root-in-the-title"></a>Jestli chcete nebo nechcete zobrazit kořenu hierarchie v názvu  
 Můžete zadat, zda se má zobrazit změnou hodnoty řádku "ShowHierarchyRootInTitle" v kořenu hierarchie v záhlaví v aplikaci *název řešení SolutionName*. Application.pkgdef soubor. Chcete-li zobrazit kořenu hierarchie, nastavte hodnotu `dword:00000001`a pokud chcete skrýt kořenu hierarchie, nastavte hodnotu `dword:00000000`.  
  
##### <a name="specifying-a-start-page"></a>Určení úvodní stránky  
 Pokud chcete zadat úvodní stránky pro vlastní aplikace, do *název řešení SolutionName*. Soubor Application.pkgdef, nastavte na hodnotu "DisableStartPage" `dword:00000000`a v části `[$RootKey$\StartPage\Default]` nastavit identifikátor URI pro umístění souboru XAML:  
  
```  
DisableStartPage=dword:00000000  
[$RootKey$\StartPage\Default]  
"Uri"="$RootFolder$\<name of XAML file>"  
```  
  
 V souboru Applicationcommands.vsct ve *název řešení SolutionName*uživatelského rozhraní projektu, komentář položku "No_ShellPkg_startPageCommand":  
  
```  
<!--<Define name="No_ShellPkg_StartPageCommand"/>-->  
```  
  
 Musíte přidat souboru XAML a všechny soubory budete potřebovat, na *název řešení SolutionName* projektu. Tyto soubory musí být ve skutečnosti zkopírují do *název řešení SolutionName* adresáři projektu, není z některé další adresáře přidat.  
  
 Na všechny soubory, nastavte **typ položky** vlastnost **izolované prostředí soubor** v pořadí pro soubory budou zkopírovány do *$RootFolder$* adresáře. (Chcete-li nastavit **typ položky** vlastnosti, klikněte pravým tlačítkem na soubor a vyberte **vlastnosti**. Tato vlastnost naleznete pod **vlastnosti konfigurace**, **Obecné**.)  
  
 Další informace o přizpůsobení úvodní stránky najdete v tématu [přizpůsobení úvodní stránky](../ide/customizing-the-start-page-for-visual-studio.md).  
  
## <a name="using-other-elements-of-the-isolated-shell"></a>Pomocí dalších prvků izolované prostředí  
 Můžete použít další soubory a projekty, které jsou součástí šablony řešení izolované prostředí k dalšímu přizpůsobení vaší aplikace.  
  
##### <a name="enabledisable-visual-studio-packages"></a>Povolí nebo zakáže balíčky Visual Studio  
 *Název řešení SolutionName*.pkgundef souboru umožňuje zakázat určité druhy funkce sady Visual Studio s výjimkou určitých balíčků. Například následující řádek:  
  
```  
[$RootKey$\Projects\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}\AddItemTemplates\TemplateDirs\{39c9c826-8ef8-4079-8c95-428f5b1c323f}]  
```  
  
 Odebere ze sady šablon projektu zobrazí v projektu ostatní soubory **nový projekt** dialogové okno. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="enabledisable-menu-commands"></a>Povolí nebo zakáže příkazy nabídky  
 *Název řešení SolutionName*UI.vsct soubor obsahuje seznam všech příkazů nabídky k dispozici pro izolované prostředí komentované. Chcete-li zakázat daného příkazu, zrušte komentář u odpovídající řádek. Například zakázat nebo rozdělení okna komentář, zrušte komentář u `<Define name="No_SplitCommand"/>` řádek. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-bitmap-used-on-the-splash-screen"></a>Rastrový obrázek použít na úvodní obrazovce  
 Můžete přizpůsobit bitové mapy použít na úvodní obrazovce, která je okno, které se zobrazí při spuštění aplikace, můžete změnit hodnotu v řádku "SplashScreenBitmap" *název řešení SolutionName*. Application.pkgdef soubor. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).  
  
##### <a name="the-helpabout-window"></a>Nápověda/o okně  
 V šabloně izolované prostředí je samostatný projekt můžete použít k přizpůsobení nápovědy/o pole pro vaši aplikaci. Další podrobnosti najdete v tématu [návod: vytvoření základní aplikace izolované prostředí](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md).