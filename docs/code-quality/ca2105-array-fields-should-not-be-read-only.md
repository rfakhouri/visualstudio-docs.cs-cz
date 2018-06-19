---
title: 'CA2105: Pole polí by neměly být pouze pro čtení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 91a97983a8760d7f5df04fe6e5b0a56a782a11ce
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31915203"
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105: Pole polí by neměly být pouze pro čtení
|||
|-|-|
|TypeName|ArrayFieldsShouldNotBeReadOnly|
|CheckId|CA2105|
|Kategorie|Microsoft.Security|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Veřejné nebo chráněného pole, které obsahuje pole je deklarovaná jen pro čtení.

## <a name="rule-description"></a>Popis pravidla
 Pokud použijete `readonly` (`ReadOnly` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) modifikátor pole, která obsahuje pole, pole nelze změnit tak, aby odkazovat na jiné pole. Avšak prvky pole, které jsou uloženy v poli určeném jen pro čtení, mohou být změněny. Ohrožení zabezpečení využitelných může obsahovat kód, který rozhoduje nebo provádí operace, které jsou založené na prvky pole jen pro čtení, která je přístupná veřejně.

 Všimněte si, že veřejné pole také porušuje pravidlo návrhu [CA1051: nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Pokud chcete vyřešit ohrožení zabezpečení, který je označený tímto pravidlem, nespoléhejte na obsah pole jen pro čtení, která veřejně přístupná. Důrazně doporučujeme použít jednu z následujících postupů:

-   Pole nahraďte silného typu kolekce, kterou nelze změnit. Další informace naleznete v tématu <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>.

-   Veřejné pole nahraďte metodu, která vrátí klon privátní pole. Protože kód nespoléhá se na klonu, nehrozí nebezpečí, pokud se změní elementy.

 Pokud jste zvolili druhý přístup, nenahrazují pole s vlastností; vlastnosti, které vracejí pole nepříznivě ovlivnit výkon. Další informace najdete v tématu [CA1819: vlastnosti by neměly vracet pole](../code-quality/ca1819-properties-should-not-return-arrays.md).

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Vyloučení upozornění od tohoto pravidla se důrazně nedoporučuje. Téměř žádné scénáře nastat, kde jsou důležitý obsah pole jen pro čtení. Pokud je tomu u váš scénář, odeberte `readonly` modifikátor místo vyloučení zprávy.

## <a name="example"></a>Příklad
 Tento příklad ukazuje nebezpečích bychom při tom porušili toto pravidlo. První část ukazuje na příkladu knihovny, která má typ, `MyClassWithReadOnlyArrayField`, který obsahuje dvě pole (`grades` a `privateGrades`) nejsou zabezpečené. Pole `grades` je veřejný a proto bude zranitelný vůči žádné volajícího. Pole `privateGrades` je privátní, ale je stále vztahují, protože se vrátí volající pomocí `GetPrivateGrades` metoda. `securePrivateGrades` Pole je vystaven bezpečným způsobem pomocí `GetSecurePrivateGrades` metoda. Je deklarován jako privátní dodržovat postupy dobrého návrhu. Druhá část ukazuje kód, který změní hodnotami uloženými v `grades` a `privateGrades` členy.

 Knihovna tříd příkladu se zobrazí v následujícím příkladu.

 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_1.cs)]

## <a name="example"></a>Příklad
 Následující kód používá knihovnu tříd příklad pro ilustraci problémy se zabezpečením pole jen pro čtení.

 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../code-quality/codesnippet/CSharp/ca2105-array-fields-should-not-be-read-only_2.cs)]

 Výstup z tohoto příkladu je:

 **Před manipulací: tříd: 90, 90, 90 stupňů privátní: 90, 90, 90 zabezpečení třídy, 90, 90 a 90**
**po manipulaci: tříd: 90, 555, 90 stupňů privátní: 90, 555, 90 zabezpečení třídy, 90, 90 a 90**
## <a name="see-also"></a>Viz také
 <xref:System.Array?displayProperty=fullName><xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>