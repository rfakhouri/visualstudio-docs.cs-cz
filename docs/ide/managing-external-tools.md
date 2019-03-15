---
title: Správa externích nástrojů
ms.date: 11/20/2017
ms.topic: conceptual
f1_keywords:
- vs.externaltools
helpviewer_keywords:
- external tools [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3562ed9ebf2d62ab002ac227486218c8c38ad337
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "57983790"
---
# <a name="manage-external-tools"></a>Správa externích nástrojů

Můžete volat z externích nástrojů v sadě Visual Studio s použitím **nástroje** nabídky. Jsou k dispozici několik výchozích nástrojů **nástroje** nabídky a můžete přizpůsobit tak, že přidáte další vlastní spustitelné soubory v nabídce.

## <a name="tools-available-on-the-tools-menu"></a>Nástroje, které jsou k dispozici v nabídce Nástroje

**Nástroje** nabídka obsahuje několik předdefinovaných příkazů, včetně:

::: moniker range="vs-2017"

* **Rozšíření a aktualizace** k [spravovat rozšíření sady Visual Studio](finding-and-using-visual-studio-extensions.md)
* **Správce fragmentů kódu** k [uspořádání fragmenty kódu](code-snippets.md)
* **Vlastní** k [přizpůsobení nabídek a panelů nástrojů](how-to-customize-menus-and-toolbars-in-visual-studio.md)
* **Možnosti** k [nastavit širokou škálu různých možností pro rozhraní IDE sady Visual Studio a další nástroje](reference/options-dialog-box-visual-studio.md)

::: moniker-end

::: moniker range=">=vs-2019"

* **Správce fragmentů kódu** k [uspořádání fragmenty kódu](code-snippets.md)
* **Vlastní** k [přizpůsobení nabídek a panelů nástrojů](how-to-customize-menus-and-toolbars-in-visual-studio.md)
* **Možnosti** k [nastavit širokou škálu různých možností pro rozhraní IDE sady Visual Studio a další nástroje](reference/options-dialog-box-visual-studio.md)

::: moniker-end

## <a name="add-new-tools-to-the-tools-menu"></a>Přidání nových nástrojů v nabídce Nástroje

Můžete přidat externího nástroje, aby se zobrazovaly na **nástroje** nabídky.

1. Otevřít **externích nástrojů** dialogové okno výběrem **nástroje** > **externích nástrojů**.

1. Klikněte na tlačítko **přidat**a potom vyplňte informace. Například způsobí, že následující položku **Windows Explorer** otevřete v adresáři souboru aktuálně máte otevřený v sadě Visual Studio:

   * Název: `Open File Location`

   * Příkaz: `explorer.exe`

   * Argumenty: `/root, "$(ItemDir)"`

   ![Dialogové okno externí nástroje](media/external-tools-dialog.png)

Následuje úplný seznam argumentů, které se dá použít při definování externího nástroje:

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
|Cílová přípona|$(TargetExt)|Přípona názvu souboru položky, která má být sestavena.|
|Binární složka|$(BinDir)|Konečné umístění binárního souboru, který má být sestaven (definované jako jednotka + cesta).|
|Adresář projektu|$(ProjectDir)|Adresář aktuálního projektu (jednotka + cesta).|
|Název souboru projektu|$(ProjectFileName)|Název souboru aktuálního projektu (jednotka + cesta + název souboru).|
|Adresář řešení|$(SolutionDir)|Adresář aktuálního řešení (jednotka + cesta).|
|Název souboru řešení|$(SolutionFileName)|Název souboru aktuálního řešení (jednotka + cesta + název souboru).|

> [!NOTE]
> Stavový řádek IDE zobrazuje **aktuálního řádku** a **aktuálního sloupce** proměnné k označení, kde se kurzor nachází v aktivním **Editor kódu**. **Aktuální Text** proměnné vrací text nebo kód vybraný v tomto umístění.

## <a name="see-also"></a>Viz také:

- [Nástroje sestavení C/C++](/cpp/build/reference/c-cpp-build-tools)
