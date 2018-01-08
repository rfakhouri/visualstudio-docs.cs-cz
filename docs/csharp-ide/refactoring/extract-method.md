---
title: "Refaktoring pro extrahování metody - (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.devlang: csharp
ms.assetid: d79d55ae-f6bb-4902-8db2-e7fe01bdb0bf
author: gewarren
ms.author: gewarren
manager: ghogen
f1_keywords: vs.csharp.refactoring.extractmethod
dev_langs: csharp
ms.workload: dotnet
ms.openlocfilehash: 44a5dd2da4cd19a532e8e6cc9f21ef48b2585fe4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="extract-a-method-in-c"></a>Extrahování metody v jazyce C# #
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
[Refaktoring (C#)](../refactoring-csharp.md)  
[Náhled změn](../../ide/preview-changes.md)