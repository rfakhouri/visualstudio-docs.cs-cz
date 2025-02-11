---
title: 'CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
helpviewer_keywords:
- CA1407
- AvoidStaticMembersInComVisibleTypes
ms.assetid: bebd0776-ad04-453c-bca8-8c124c2d7840
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 631be1a93318cd24af4251fefbc710294fa52bf7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922014"
---
# <a name="ca1407-avoid-static-members-in-com-visible-types"></a>CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM

|||
|-|-|
|TypeName|AvoidStaticMembersInComVisibleTypes|
|CheckId|CA1407|
|Kategorie|Microsoft. interoperabilita|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
Typ, který je konkrétně označen jako viditelný pro model COM (Component Object Model) obsahuje `public``static` metodu.

## <a name="rule-description"></a>Popis pravidla
Model COM nepodporuje `static` metody.

Toto pravidlo ignoruje přístupové objekty vlastností a událostí, metody přetížení operátoru nebo metody, které jsou označeny pomocí <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute?displayProperty=fullName> atributu <xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute?displayProperty=fullName> nebo atributu.

Ve výchozím nastavení jsou následující prvky viditelné v modelu COM: sestavení, veřejné typy, členy veřejné instance ve veřejných typech a všechny členy typů veřejné hodnoty.

Aby toto pravidlo bylo provedeno, musí být na úrovni <xref:System.Runtime.InteropServices.ComVisibleAttribute> sestavení nastavena na `false` a třída <xref:System.Runtime.InteropServices.ComVisibleAttribute> musí být nastavena na `true`, jak ukazuje následující kód.

```csharp
using System;
using System.Runtime.InteropServices;

[assembly: ComVisible(false)]
namespace Samples
{
    [ComVisible(true)]
    public class MyClass
    {
        public static void DoSomething()
        {
        }
    }
}
```

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, změňte návrh tak, aby používal metodu instance, která poskytuje stejné funkce jako `static` metoda.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
V případě, že klient modelu COM nevyžaduje přístup k funkcím, které poskytuje `static` metoda, je bezpečné potlačit upozornění od tohoto pravidla.

## <a name="example-violation"></a>Příklad porušení

### <a name="description"></a>Popis
Následující příklad ukazuje `static` metodu, která porušuje toto pravidlo.

### <a name="code"></a>Kód
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersViolation#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_1.cs)]

### <a name="comments"></a>Komentáře
V tomto příkladu nelze volat metodu **Book. FromPages** z modelu COM.

## <a name="example-fix"></a>Příklad opravy

### <a name="description"></a>Popis
Chcete-li opravit porušení v předchozím příkladu, můžete změnit metodu na metodu instance, která ale v této instanci nedává smysl. Lepším řešením je výslovně použít `ComVisible(false)` tuto metodu, aby bylo jasné, že nepůjde z modelu COM vyjasnit jiným vývojářům.

Následující příklad se vztahuje <xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute> na metodu.

### <a name="code"></a>Kód
[!code-csharp[FxCop.Interoperability.ComVisibleStaticMembersFixed#1](../code-quality/codesnippet/CSharp/ca1407-avoid-static-members-in-com-visible-types_2.cs)]

## <a name="related-rules"></a>Související pravidla
[CA1017: Označte sestavení pomocí ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

[CA1406: Vyhněte se argumentům Int64 pro klienty Visual Basic 6](../code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients.md)

[CA1413: Vyhněte se neveřejným polím v viditelných hodnotových typech modelu COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

## <a name="see-also"></a>Viz také:
[Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)