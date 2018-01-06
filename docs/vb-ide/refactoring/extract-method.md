---
title: "Extrahování metody - refaktoringu (Visual Basic) | Microsoft Docs"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: VB
ms.assetid: 8ad16c15-432b-4b8c-86fd-5f31ad652d24
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: VB
ms.workload: multiple
ms.openlocfilehash: 6ec25b8c0e2a583364ff3c6418515507cdc04d40
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extract-a-method-in-visual-basic"></a>Extrahování metody v jazyce Visual Basic
**Co:** umožňuje zapnout fragment kódu do své vlastní metody.

**Kdy:** máte fragment kódu existující v některé metody, které musí být volána z jiné metody.  

**Důvod:** vám může zkopírujte a vložte tento kód, ale které by vedlo k duplikaci.  Lepší řešení je refaktorovat tento fragment do vlastní metodu, která můžete volně volána jiným způsobem.

**Postupy:**

1. Zvýrazněte kód extrahovat:

   ![Zvýrazněný kód](media/extractmethod_highlight.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl + R**, pak **Ctrl + M**.  (Všimněte si, že klávesové zkratky se může lišit na základě na profilu, které jste vybrali.)
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **extrahovat metodu** z okna náhledu – místní nabídka.
   * **Myš**
     * Vyberte **Upravit > Refaktorovat > extrahování metody**.
     * Klikněte pravým tlačítkem na kód a vyberte **Refaktorovat > extrahovat > extrahovat metodu**.
     * Klikněte pravým tlačítkem na kód, vyberte **rychlé akce a refaktoring** nabídku a vyberte **extrahovat metodu** z okna náhledu – místní nabídka.

   Metoda se okamžitě vytvoří.  Tady můžete nyní přejmenovat metoda jednoduše tak, že zadáte nový název.

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců používat tento nový název, a také [zobrazení náhledu změn](../../ide/preview-changes.md) před uložením pomocí zaškrtávacích políček v **přejmenovat** pole, která se zobrazí v horní části napravo od vaší IDE.

   ![Přejmenujte – metoda](media/extractmethod_rename.png)

1. Jakmile budete spokojeni se změnami, klikněte na **použít** tlačítko nebo klikněte na tlačítko **Enter** a změny budou potvrzeny.

## <a name="see-also"></a>Viz také  
[Refaktoringu (Visual Basic)](../refactoring-vb.md)  
[Náhled změn](../../ide/preview-changes.md)