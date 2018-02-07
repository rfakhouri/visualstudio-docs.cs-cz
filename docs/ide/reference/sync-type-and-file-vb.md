---
title: "Synchronizovat typ a název souboru v jazyce Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 02/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 93e1b1f446dc330b2c2c1c1e5b36e6a21e64f521
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="sync-a-type-to-a-filename-or-a-filename-to-a-type-in-visual-basic"></a>Synchronizovat typu pro název souboru nebo název souboru na typ v jazyce Visual Basic

<!-- VERSIONLESS -->
**Tato funkce je k dispozici v aplikaci Visual Studio 2017 a novějším.  Kromě toho se pro tento refaktoring ještě nepodporuje .NET Standard projekty.**

**Co:** umožňuje přejmenujte typ k porovnání název souboru, nebo název souboru tak, aby odpovídaly typ obsahuje.

**Kdy:** přejmenovaná souboru nebo typ a ještě neprovedli aktualizaci na odpovídající soubor nebo typ k porovnání. 

**Důvod:** umístění a typ v souboru s jiným názvem nebo naopak, je obtížné najít, co hledáte.  Přejmenováním typ nebo název souboru, bude kód čitelnější a snadný přechod.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do název typu synchronizovat:

   ![Zvýrazněný kód](media/synctype-highlight-vb.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **přejmenování souboru *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     * Stiskněte klávesu **Ctrl +.** k aktivační události **rychlé akce a refaktoring** nabídku a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde *Filename* je název aktuálního souboru.
   * **Myš**
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **přejmenování souboru *TypeName*VB** z místní okno náhledu, kde *TypeName* je název typu, který jste vybrali.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídce a vyberte **Přejmenovat typ _Filename_**  z místní okno náhledu, kde  *Název souboru* je název aktuálního souboru.

   Typ nebo soubor okamžitě se přejmenuje.  V příkladu níže soubor **Employee.vb** byla přejmenována na **Person.vb** tak, aby odpovídaly název typu.

   ![Vložené výsledek](media/synctype-result-vb.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)
