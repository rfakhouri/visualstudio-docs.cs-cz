---
title: 'CA2213: Uvolnitelná pole by měla být uvolněna'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- DisposableFieldsShouldBeDisposed
- CA2213
helpviewer_keywords:
- CA2213
- DisposableFieldsShouldBeDisposed
ms.assetid: e99442c9-70e2-47f3-b61a-d8ac003bc6e5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b38157fcc23561b47a919151aa78a71f98b3909b
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65805002"
---
# <a name="ca2213-disposable-fields-should-be-disposed"></a>CA2213: Uvolnitelná pole by měla být uvolněna

|||
|-|-|
|TypeName|DisposableFieldsShouldBeDisposed|
|CheckId|CA2213|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> deklaruje pole, která jsou typy, které také implementují <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Není volána metoda pole <xref:System.IDisposable.Dispose%2A> metoda deklarujícího typu.

## <a name="rule-description"></a>Popis pravidla

Typ je zodpovědná za uvolnění všech nespravovaných prostředků. Pravidlo CA2213 kontroluje, zda uvolnitelného typu (to znamená, jednu, která implementuje <xref:System.IDisposable>) `T` deklaruje pole `F` z uvolnitelného typu, který je instance `FT`. Pro každé pole `F` , které se má přiřadit místně vytvořený objekt v rámci metody nebo inicializátory nadřazeného typu `T`, pravidlo se pokusí najít volání `FT.Dispose`. Toto pravidlo vyhledá metody volané `T.Dispose` a jednu úroveň níže (to znamená, volání metody volané metody `T.Dispose`).

> [!NOTE]
> Než [zvláštní případy](#special-cases), pravidlo CA2213 je aktivována pouze pro pole, které jsou přiřazeny místně vytvořené uvolnitelný objekt v rámci nadřazeného typu metody a inicializátory. Pokud je objekt vytvořen nebo přiřazené mimo typ `T`, pravidlo se neaktivuje. To snižuje šumu pro případy, kdy nadřazeného typu nevlastní odpovědnost za uvolnění objektu.

### <a name="special-cases"></a>Zvláštní případy

CA2213 pravidlo můžete platit také pro pole z následujících typů i v případě, že objekt, který je přiřazený není vytvořeno místně:

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

Předání objektu jednoho z těchto typů konstruktoru a pak ji přiřadíte do pole označuje *dispose převod vlastnictví* do nově konstruovaný typ. To znamená je nově konstruovaný typ nyní zodpovědná za uvolnění objektu. Pokud není uvolněn, dojde k narušení CA2213.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

Chcete-li opravit porušení tohoto pravidla, zavolejte <xref:System.IDisposable.Dispose%2A> pro pole, která jsou typy, které implementují <xref:System.IDisposable>.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

Je bezpečné potlačit upozornění tohoto pravidla, pokud:

- Typ s příznakem nezodpovídá za uvolnění prostředku drží pole (to znamená, typ nemá *dispose vlastnictví*)
- Volání <xref:System.IDisposable.Dispose%2A> dochází na hlubší úrovni volání než pravidla kontroly

## <a name="example"></a>Příklad

Následující fragment kódu ukazuje typ `TypeA` , který implementuje <xref:System.IDisposable>.

[!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_1.cs)]

Následující fragment kódu ukazuje typ `TypeB` , který porušuje pravidla CA2213 deklarováním pole `aFieldOfADisposableType` jako uvolnitelného typu (`TypeA`) a není volání <xref:System.IDisposable.Dispose%2A> na pole.

[!code-csharp[FxCop.Usage.IDisposableFields#1](../code-quality/codesnippet/CSharp/ca2213-disposable-fields-should-be-disposed_2.cs)]

## <a name="see-also"></a>Viz také:

- <xref:System.IDisposable?displayProperty=fullName>
- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)