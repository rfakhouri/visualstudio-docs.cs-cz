---
title: Zobrazení náhledu změn kódu v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 12/16/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.codefix.previewchanges
ms.workload:
- multiple
ms.openlocfilehash: cc838d55e83a5b606059acbf068639116ab012bd
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="preview-changes-window"></a>Okno náhledu změny

Při použití různých *rychlé akce* nebo *Refactoring* nástroje v sadě Visual Studio, je často možné zobrazení náhledu změn, které se chystáte provést do projektu před přijetím je. **Zobrazení náhledu změn** je okno, kde je to provést.  Zde je ukázka, **zobrazení náhledu změn** okno zobrazuje, co se změní při přejmenování refactor v projektu C#:

![Zobrazení náhledu změn](media/previewchanges.png)

V horní polovině okna zobrazí konkrétní řádky, které se změní, každý s zaškrtávací políčko. Dokáže kontrolovat nebo zrušte zaškrtnutí políčka každý zaškrtávací políčko, pokud chcete selektivně používají refaktoring pouze konkrétní řádcích.

Dolní polovinu okna zobrazuje formátovaný kód z projektu, který se změní, s ovlivněných oblasti zvýrazněná. Výběr konkrétní řádek v horní polovině okna zvýrazní odpovídající řádek v dolní části půl. To umožňuje rychle přeskočit na příslušný řádek a zobrazit okolního kód.

Po zkontrolování změn, klikněte na tlačítko **použít** tlačítko tyto změny potvrdit, nebo klikněte na tlačítko **zrušit** tlačítka opustit věci, jako.

## <a name="see-also"></a>Viz také

[Refaktoring v sadě Visual Studio](../ide/refactoring-in-visual-studio.md)  
[Rychlé akce](../ide/quick-actions.md)
