---
title: "Generování rovná a metoda GetHashCode přepsání – generování kódu (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 56b1753dbdcfbf8ce318e964a16879f02b1482c4
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/06/2018
---
# <a name="generate-equals-and-gethashcode-method-overrides-in-c"></a>Generovat rovná a metoda GetHashCode přepsání v jazyce C# #

**Co:** umožňuje vygenerovat **rovná** a **GetHashCode** metody.

**Kdy:** generovat tato přepsání, až budete mít typ, který reprezentuje "hodnotu", která by měla být ve srovnání některá pole místo podle umístění objektu v paměti.

**Důvod:** při implementaci typ hodnoty, měli byste zvážit přepsání metody Equals k získání vyšší výkon přes výchozí implementace metody Equals na typ hodnoty.

Pokud implementujete odkazového typu, měli byste zvážit přepsání metody Equals, pokud typ vašeho vypadá jako základní typ, jako je například bod, řetězec, BigNumber a tak dále.

Potlačí metodu GetHashCode umožňující typu fungovat správně v zatřiďovací tabulku. Přečtěte si další pokyny [operátory rovnosti](/dotnet/standard/design-guidelines/equality-operators).

**Postupy:**

1. Umístěte kurzor vaší deklaraci typu.

   ![Zvýrazněný kód](media/overrides-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídku a vyberte **generovat Equals(object)** nebo **generovat rovná se a GetHashCode** z okna náhledu – místní nabídka.
   * **Myš**
     * Klikněte pravým tlačítkem a vyberte **rychlé akce a refaktoring** nabídku a vyberte **generovat Equals(object)** nebo **generovat rovná se a GetHashCode** z okna náhledu místní nabídka.
     * Klikněte ![Žárovek](media/bulb-cs.png) ikonu, která se zobrazí na levém okraji, pokud je text kurzor již na ose s deklarace typu.

   ![Vytvoření náhledu přepsání](media/overrides-preview-cs.png)

1. Vyberte členy, které chcete generovat přepsání metody pro:

    ![Generovat přepsání dialogové okno](media/overrides-dialog-cs.png)

    > [!TIP]
    > Můžete také vygenerovat operátory z tohoto dialogového okna pomocí zaškrtávacích políček pod seznam členů.

1. Rovná se a GetHashCode přepsání se vygeneruje s automatické výchozí implementace.

   ![Generování výsledků – metoda](media/overrides-result-cs.png)

## <a name="see-also"></a>Viz také

[Generování kódu](../code-generation-in-visual-studio.md)  
[Náhled změn](../../ide/preview-changes.md)
