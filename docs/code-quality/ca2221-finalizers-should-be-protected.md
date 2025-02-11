---
title: 'CA2221: Finalizační metody by měly být chráněné'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e88f22f25ff0620a88685dee93fd5658c302db74
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920245"
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221: Finalizační metody by měly být chráněné

|||
|-|-|
|TypeName|FinalizersShouldBeProtected|
|CheckId|CA2221|
|Kategorie|Microsoft.Usage|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina
Veřejný typ implementuje finalizační metodu, která neurčuje přístup Family (Protected).

## <a name="rule-description"></a>Popis pravidla
Finalizační metody musí použít modifikátor přístupu family. Toto pravidlo je vynutilo kompilátory C#, Visual Basic a Visual C++ .

## <a name="how-to-fix-violations"></a>Jak opravit porušení
Chcete-li opravit porušení tohoto pravidla, změňte finalizační metodu tak, aby byla přístupná pro rodinu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
Toto pravidlo se nedá porušovat v žádném jazyce .NET úrovně vyšší úrovně; může být porušena, pokud píšete Microsoft Intermediate Language.

```
// =============== CLASS MEMBERS DECLARATION ===================
//   note that class flags, 'extends' and 'implements' clauses
//          are provided here for information only

.namespace UsageLibrary
{
  .class public auto ansi beforefieldinit FinalizeMethodNotProtected
         extends [mscorlib]System.Object
  {
    .method public hidebysig instance void
            Finalize() cil managed
    {

      // Code size       1 (0x1)
      .maxstack  0
      IL_0000:  ret
    } // end of method FinalizeMethodNotProtected::Finalize

    .method public hidebysig specialname rtspecialname
            instance void  .ctor() cil managed
    {
      // Code size       7 (0x7)
      .maxstack  1
      IL_0000:  ldarg.0
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
      IL_0006:  ret
    } // end of method FinalizeMethodNotProtected::.ctor

  } // end of class FinalizeMethodNotProtected
} // end of namespace
```

## <a name="see-also"></a>Viz také:

- [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)