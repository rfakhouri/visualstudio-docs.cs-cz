---
title: Dokončování příkazů ve službě starší verze jazyka | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- statement completion
- language services, statement completion
ms.assetid: 617439dc-3f0e-4e5f-b346-3e4e7fcf3c1b
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5c6e157505b146b9c1ca37f508311c9e80958be6
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322438"
---
# <a name="statement-completion-in-a-legacy-language-service"></a>Dokončování příkazů ve službě starší verze jazyka
Doplňování výrazů je proces, podle kterého jazyková služba pomáhá uživatelům dokončit – klíčové slovo jazyka nebo element, kterou zahájil psaní v editoru core. Toto téma popisuje, jak dokončování funguje a jak implementovat ve vaší službě jazyka.

 Služby starší verze jazyka jsou implementovány jako součást sady VSPackage, ale novější způsob implementace funkce služba jazyka je pro použití rozšíření MEF. Další informace o nový způsob implementace dokončování příkazů najdete v tématu [názorný postup: Zobrazení dokončování příkazů](../../extensibility/walkthrough-displaying-statement-completion.md).

> [!NOTE]
> Doporučujeme vám, že začnete používat nový editor API co nejdříve. Tím vylepšíme výkonu vaší služby jazyka a umožňují využívat nové funkce editoru.

## <a name="implementing-statement-completion"></a>Implementace dokončování příkazů
 Dokončování příkazů v základní editor aktivuje speciální uživatelské rozhraní, které interaktivně vám pomůže snadno a rychle psát kód. Dokončování příkazů pomáhá zobrazením relevantní objekty nebo třídy když potřeba jsou, díky tomu není, můžete si museli pamatovat konkrétní prvky nebo by bylo nutné je vyhledat v referenčním tématu nápovědy.

 K implementaci dokončování příkazů, musí mít váš jazyk trigger dokončení příkazu, který může být analyzován. Například [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] pomocí operátoru tečka (.), zatímco [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] používá šipka (->) – operátor. Služba jazyka slouží k zahájení dokončení příkazu více než jeden trigger. Tyto triggery jsou naprogramovány příkaz filtru.

## <a name="command-filters-and-triggers"></a>Příkaz filtry a aktivačních událostí
 Příkaz filtry zachytit výskytů aktivační události nebo aktivační události. Chcete-li přidat příkaz Filtr na zobrazení, implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní a připojí ho k zobrazení pomocí volání <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.AddCommandFilter%2A> metody. Můžete použít stejný příkaz Filtr (<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>) pro všechny aspekty vaší služby jazyka, jako je doplňování výrazů, označování chyb a metoda tipy. Další informace najdete v tématu [zachycování příkazy služby starší verze jazyka](../../extensibility/internals/intercepting-legacy-language-service-commands.md).

 Když se zadá aktivační události v editoru – konkrétně textovou vyrovnávací paměť – vaše služba jazyka je pak zavolá <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.UpdateCompletionStatus%2A> – metoda. To způsobí, že editor zobrazíte uživatelského rozhraní tak, aby uživatel může zvolit z kandidáty dokončení příkazu. Tato metoda vyžaduje, abyste k implementaci <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> a <xref:Microsoft.VisualStudio.TextManager.Interop.UpdateCompletionFlags> příznaky jako parametry. V rozbalovacím seznamu se zobrazí seznam položek dokončení. Uživatel se stále psát a výběr v seznamu se aktualizuje tak, aby odrážely zadali nejvíce odpovídá nejnovější znaků. Základní editor implementuje v uživatelském rozhraní dokončování příkazů, ale musí implementovat služba jazyka <xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompletionSet> rozhraní k definování sady položek dokončení Release candidate pro příkaz.

## <a name="see-also"></a>Viz také
- [Příkazy zachytávání služby starší verze jazyka](../../extensibility/internals/intercepting-legacy-language-service-commands.md)