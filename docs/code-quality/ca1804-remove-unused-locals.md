---
title: 'CA1804: Odeberte nepoužívané lokální hodnoty'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4e7e82d6d631f12733e75262050afc66fb844416
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54999194"
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: Odeberte nepoužívané lokální hodnoty

|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|Kategorie|Microsoft.Performance|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Metoda deklaruje místní proměnnou, ale nepoužívá proměnnou s výjimkou pravděpodobně jako příjemce příkazu přiřazení. Pro analýzu tímto pravidlem testované sestavení musí být sestaveny s ladicími informacemi a přidružené programového souboru databáze (PDB) musí být k dispozici.

## <a name="rule-description"></a>Popis pravidla
 Nepoužívané místní proměnné a zbytečná přiřazení zvětšují velikost sestavení a snižují výkon.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, odeberte nebo použijte místní proměnnou. Všimněte si, že kompilátor jazyka C#, která je součástí [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] odebere nepoužívané místní proměnné při `optimize` je povolená možnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Potlačit upozornění tohoto pravidla, je-li proměnná byla kompilátoru, protože ho. Je také bezpečné upozornění tohoto pravidla můžete potlačit nebo zakážete pravidlo, pokud výkon a údržba kódu nejsou primární obavy.

## <a name="example"></a>Příklad
 Následující příklad ukazuje několik nepoužívané místní proměnné.

 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>Související pravidla
 [CA1809: Vyhněte se nadměrným místním hodnotám](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811: Vyhněte se nevolanému místnímu kódu](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: Vyhněte se nevytvořeným instancím vnitřních tříd](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: Revize nepoužitých parametrů](../code-quality/ca1801-review-unused-parameters.md)