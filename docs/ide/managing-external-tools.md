---
title: "Správa externích nástrojů | Microsoft Docs"
ms.custom: 
ms.date: 11/20/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.externaltools
helpviewer_keywords:
- external tools [Visual Studio]
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 78a3e1ee549a42681d6f15b432d0c6bb608976fd
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="manage-external-tools"></a>Správa externích nástrojů

Můžete volat z externích nástrojů v sadě Visual Studio pomocí **nástroje** nabídky. Několik výchozí nástroje jsou k dispozici na **nástroje** nabídce a můžete upravit v nabídce přidáním další spustitelné soubory vlastní.

## <a name="tools-available-on-the-tools-menu"></a>Nástroje dostupné v nabídce Nástroje

**Nástroje** nabídky obsahuje několik předdefinovaných příkazy, jako například:

* **Rozšíření a aktualizace** pro [Správa rozšíření v jazyce Visual Studio](finding-and-using-visual-studio-extensions.md)
* **Správce fragmentů kódu...**  pro [uspořádání fragmenty kódu](code-snippets.md)
* **Preemptivní ochrana – Dotfuscatoru** pro spuštění [Dotfuscatoru Community Edition (CE)](dotfuscator/index.md) Pokud je [nainstalován](dotfuscator/install.md)
* **Vlastní nastavení...**  pro [přizpůsobení nabídek a panelů nástrojů](how-to-customize-menus-and-toolbars-in-visual-studio.md)
* **Možnosti...**  pro [nastavení celou řadu různých možností pro Visual Studio IDE a dalších nástrojů](reference/options-dialog-box-visual-studio.md)

## <a name="add-new-tools-to-the-tools-menu"></a>Přidání nových nástrojů do nabídky Nástroje

Můžete přidat externího nástroje se objevily na **nástroje** nabídky.

1. Otevřete **externích nástrojů** dialogové okno a vybrat **nástroje** > **externích nástrojů...** .

1. Klikněte na tlačítko **přidat**a pak zadejte informace. Následující položka například způsobí otevření programu Průzkumník Windows v adresáři souboru aktuálně otevřeného v aplikaci Visual Studio:

   * Název:`Open File Location`

   * Příkaz:`explorer.exe`

   * Argumenty:`/root, "$(ItemDir)"`

   ![Dialogové okno externí nástroje](media/external-tools-dialog.png)

Následuje úplný seznam argumentů, které lze použít při definování externího nástroje:

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
|Binární složka|$(BinDir)|Konečné umístění binárního souboru, který má být sestaven (definované jako jednotka + cesta).|  
|Adresář projektu|$(ProjDir)|Adresář aktuálního projektu (jednotka + cesta).|  
|Název souboru projektu|$(ProjFileName)|Název souboru aktuálního projektu (jednotka + cesta + název souboru).|  
|Adresář řešení|$(SolutionDir)|Adresář aktuálního řešení (jednotka + cesta).|  
|Název souboru řešení|$(SolutionFileName)|Název souboru aktuálního řešení (jednotka + cesta + název souboru).|

> [!NOTE]
> Stavový řádek IDE zobrazuje pro označení místa bodu vložení v aktivním editoru kódu proměnné Current Line a Current Column. Proměnná Current Text vrací text nebo kód vybraný v rámci tohoto místa.

## <a name="see-also"></a>Viz také

[Nástroje sestavení C/C++](/cpp/build/reference/c-cpp-build-tools)
