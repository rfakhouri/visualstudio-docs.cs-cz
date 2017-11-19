---
title: "Správa externích nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.externaltools
helpviewer_keywords:
- Create GUID tool
- RC (Resource Compiler)
- ReBase tool
- Windows NT Message Compiler
- Windows NT C++ Symbol Undecorator
- tstcon32.exe
- Type Library Generator
- Windows NT Image Binder
- tools [Visual Studio], external
- RowsetViewer tool
- utilities, external tools
- Local Test Manager
- OLE DB Rowset Viewer
- Midlc (IDL Compiler)
- ATL Trace Tool
- Odbcte32w.exe
- IDL Compiler
- HCW (Help Workshop)
- Message Compiler [Visual Studio]
- UUID Generator
- MIDL, external tools
- ErrLook tool
- MAKEHM tool
- Error lookup tool
- OLEVIEW (Object Viewer)
- Uuidgen.exe
- WebDbg tool
- OLE/COM Object Viewer
- LTM (Local Test Manager)
- ATLTraceTool.exe
- Bind tool
- Vsvars32.bat
- external tools [Visual Studio]
- ODBC Test
- Windows NT Image Rebaser
- undname.exe
- Vcspawn.exe
- ActiveX Control Test Container
- mc (Message Compiler)
- GUIDGEN tool
- Odbcte32.exe
- DisableMsg tool
- MkTypLib tool
- Help Workshop
- Resource Compiler
ms.assetid: f382fd40-a98f-4934-8c9a-5aeae881acde
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9829887a28ec2e672999732e38604f3d9d6fea9a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="manage-external-tools"></a>Správa externích nástrojů
Můžete volat z externích nástrojů v sadě Visual Studio pomocí **nástroje** nabídky. Několik výchozí nástroje jsou k dispozici na **nástroje** nabídce, ale můžete přidat další spustitelné soubory vlastní.  

## <a name="tools-available-on-the-visual-studio-tools-menu"></a>Nástroje dostupné v nabídce Nástroje sady Visual Studio
 **Nástroje** nabídky obsahuje několik předdefinovaných příkazy, jako například:

*  **Rozšíření a aktualizace** pro [Správa rozšíření v jazyce Visual Studio](finding-and-using-visual-studio-extensions.md)
*  **Správce fragmentů kódu...**  pro [uspořádání fragmenty kódu](code-snippets.md#code-snippet-manager)
*  **Preemptivní ochrana – Dotfuscatoru** pro spuštění [Dotfuscatoru Community Edition (CE)](dotfuscator/index.md) Pokud je [nainstalován](dotfuscator/install.md)
*  **Vlastní nastavení...**  pro [přizpůsobení nabídek a panelů nástrojů](how-to-customize-menus-and-toolbars-in-visual-studio.md)
*  **Možnosti...**  pro [nastavení celou řadu různých možností pro Visual Studio IDE a dalších nástrojů](reference/options-dialog-box-visual-studio.md)

## <a name="add-new-tools-to-the-tools-menu"></a>Přidání nových nástrojů do nabídky Nástroje 
 Můžete přidat externí nástroj pro **nástroje** nabídky. Otevřete **externích nástrojů...**  dialogové okno a klikněte na tlačítko **přidat**, potom vyplňte informace. Následující položka například způsobí otevření programu Průzkumník Windows v adresáři souboru aktuálně otevřeného v aplikaci Visual Studio:  
  
1.  Title: *Otevřít umístění souboru*
  
2.  Příkaz:`explorer.exe`  
  
3.  Argumenty:`/root, "$(ItemDir)"`  
  
 Následuje úplný seznam argumentů, které lze použít při definování externího nástroje.
  
> [!NOTE]
>  Stavový řádek IDE zobrazuje pro označení místa bodu vložení v aktivním editoru kódu proměnné Current Line a Current Column. Proměnná Current Text vrací text nebo kód vybraný v rámci tohoto místa.  
  
|Název|Argument|Popis|  
|----------|--------------|-----------------|  
|Cesta položky|$(ItemPath)|Celý název souboru aktuálního souboru (jednotka + cesta + název souboru).|  
|Adresář položky|$(ItemDir)|Adresář aktuálního souboru (jednotka + cesta).|  
|Název souboru položky|$(ItemFilename)|Název aktuálního souboru (název souboru).|  
|Přípona položky|$(ItemExt)|Název přípony aktuálního souboru.|  
|Aktuální řádek|$(CurLine)|Pozice aktuálního řádku v kurzoru v okně kódu.|  
|Aktuální sloupec|$(CurCol)|Pozice aktuálního sloupce v kurzoru v okně kódu.|  
|Aktuální text|$(CurText)|Vybraný text.|  
|Cílová cesta|$(TargetPath)|Úplný název souboru položky, která má být sestavena (jednotka + cesta + název souboru).|  
|Cílový adresář|$(TargetDir)|Adresář položky, která má být sestavena.|  
|Cílový název|$(TargetName)|Název souboru položky, která má být sestavena.|  
|Přípona cílového|$(TargetExt)|Přípona názvu souboru položky, která má být sestavena.|  
|Binární složka|$(BinDir)|Konečné umístění binárního souboru, který má být sestaven (definované jako jednotka + cesta). Příklad:**\\... \My Documents\Visual Studio \<verze >\\< název projektu\>\bin\debug**|  
|Adresář projektu|$(ProjDir)|Adresář aktuálního projektu (jednotka + cesta).|  
|Název souboru projektu|$(ProjFileName)|Název souboru aktuálního projektu (jednotka + cesta + název souboru).|  
|Adresář řešení|$(SolutionDir)|Adresář aktuálního řešení (jednotka + cesta).|  
|Název souboru řešení|$(SolutionFileName)|Název souboru aktuálního řešení (jednotka + cesta + název souboru).|  

## <a name="see-also"></a>Viz také  
 [Nástroje sestavení C/C++](/cpp/build/reference/c-cpp-build-tools)
