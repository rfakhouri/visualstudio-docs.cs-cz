---
title: Ladění pomocí Prohlížeče ukládání
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, store viewer
- Domain-Specific Language, store
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: c46e84caba16abbe9ba9d166076d1ee48d34fd94
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-by-using-the-store-viewer"></a>Ladění pomocí Prohlížeče ukládání
S prohlížeč uložit, můžete zkontrolovat stav *ukládání* používá [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]. Uložení prohlížeč zobrazí všechny prvky modelu domény, které jsou v určitém úložišti, spolu s vlastností elementů a odkazů mezi elementy.

## <a name="opening-store-viewer"></a>Prohlížeč otevírání úložiště
 Pokud pracujete s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] experimentální sestavení, zastavte kódu na zarážce, kde instance úložiště obsahuje informace o modelu. Potom otevřete prohlížeč úložiště zadáním následujícího příkazu v **Immediate** okno:

```
Microsoft.VisualStudio.Modeling.Diagnostics.StoreViewer.Show(mystore);
```

> [!NOTE]
>  Je třeba nahradit `mystore` s názvem instance vašeho úložiště. Navíc pokud přidáte obor názvů do kódu, můžete zadat příkaz pro zobrazení prohlížeče úložiště bez plně kvalifikovaný obor názvů:
>
>  `using Microsoft.VisualStudio.Modeling.Diagnostics;`
>
>  `...`
>
>  `StoreViewer.Show(mystore);`

 `Show` Metoda má několik přetížení. Instance úložiště nebo oddíl můžete zadat jako parametr.

 Jako alternativu, které můžete vložit řádek kódu, které se zobrazí v prohlížeči úložiště kdekoli v kódu kde parametr, který můžete předat `Show` metoda je v oboru. Tato akce zobrazí prohlížeč uložit, když se provede na řádek kódu jako snímek obsahu úložiště.

### <a name="using-store-viewer"></a>Pomocí prohlížeče úložiště
 Když se otevře v prohlížeči úložiště, zobrazí se nemodálním okně Windows Forms jak ukazuje následující obrázek.

 ![](../modeling/media/storeviewer2.png "storeviewer2") ukládání prohlížeč

 V prohlížeči úložiště má tři podokna: levém podokně, podokně pravém horním a pravém dolním podokně. V levém podokně se stromovou strukturu typy v `DomainDataDirectory` člena pro úložiště. Rozbalte uzel oddílu a klikněte na tlačítko elementu, elementu vlastnosti se zobrazí v pravém podokně. Pokud element je propojený na další prvky, další prvky se zobrazí v pravém dolním podokně. Pokud dvakrát kliknete na element v pravém dolním podokně element zvýrazní v levém podokně.

## <a name="see-also"></a>Viz také

- [Navigace v modelu a aktualizace modelu v kódu programu](../modeling/navigating-and-updating-a-model-in-program-code.md)