---
title: "Nahraďte proměnnou dočasné s hodnotou v jazyce C# | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 626224e8ed90196294f7b3ded245bb5272f70595
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="inline-a-temporary-variable-with-c"></a>Vložené dočasnou proměnnou pomocí C# #

**Co:** umožňuje odebrání dočasné proměnné a nahraďte ji metodou jeho hodnotu.

**Kdy:** použití dočasné proměnné díky těžší pochopit kód.

**Důvod:** odebrání dočasné proměnné může usnadnit kód čtení.

**Postupy:**

1. Zvýrazněte nebo umístěte kurzor text do dočasné proměnné být vložená:

   ![Zvýrazněný kód](media/inline-highlight-cs.png)

1. Dále proveďte jednu z následujících akcí:
   * **Klávesnice**
     * Stiskněte klávesu **Ctrl +.** spuštění **rychlé akce a refaktoring** nabídky.
   * **Myš**
     * Klikněte pravým tlačítkem na kód a vyberte **rychlé akce a refaktoring** nabídky.

1. Vyberte **dočasné vloženou proměnnou** z okna náhledu – místní nabídka.

   Proměnná se odeberou a jeho použití nahrazen hodnotou proměnné okamžitě.

   ![Vložené výsledek](media/inline-result-cs.png)

## <a name="see-also"></a>Viz také

[Refactoring](../refactoring-in-visual-studio.md)