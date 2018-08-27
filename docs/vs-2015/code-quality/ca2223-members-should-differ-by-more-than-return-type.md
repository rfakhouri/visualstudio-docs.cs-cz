---
title: 'CA2223: Členy by se měly lišit o více než návratový typ | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MembersShouldDifferByMoreThanReturnType
- CA2223
helpviewer_keywords:
- CA2223
- MembersShouldDifferByMoreThanReturnType
ms.assetid: eb326d9f-50d9-48cb-84be-d41c84a8fe09
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: baa4f49487fde1ea38ad7362c8941d15868abec7
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902264"
---
# <a name="ca2223-members-should-differ-by-more-than-return-type"></a>CA2223: Členy by se měly lišit o více než návratový typ
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2223: členy by se měly lišit o více než návratový typ](https://docs.microsoft.com/visualstudio/code-quality/ca2223-members-should-differ-by-more-than-return-type).

|||
|-|-|
|TypeName|MembersShouldDifferByMoreThanReturnType|
|CheckId|CA2223|
|Kategorie|Microsoft.Usage|
|Narušující změna|Narušující|

## <a name="cause"></a>příčina
 Dvě veřejné nebo chráněné členy mají podpisy, které jsou stejné s výjimkou návratovým typem.

## <a name="rule-description"></a>Popis pravidla
 I když se modul common language runtime umožňuje používat návratové typy k rozlišení mezi jinak identickými členy, tato funkce není v Common Language Specification ani je to běžná funkce programovacích jazycích rozhraní .NET. Když členové liší pouze návratovým typem, vývojáře a nástroje pro vývoj nemusí správně mezi nimi rozlišovat.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, změňte návrh členů tak, aby byly jedinečné, pouze na základě jejich názvy a typy parametrů, nebo nezveřejňujte členy.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění na toto pravidlo.

## <a name="example"></a>Příklad
 Následující příklad ukazuje v jazyk Microsoft intermediate language (MSIL), typ, který porušuje tato pravidla. Všimněte si, že nelze toto pravidlo porušeno pomocí jazyka C# nebo Visual Basic .NET.

```

.namespace UsageLibrary
{
  .class public auto ansi beforefieldinit ReturnTypeTest
         extends [mscorlib]System.Object
  {
    .method public hidebysig instance int32
            AMethod(int32 x) cil managed
    {
      // Code size       6 (0x6)
      .maxstack  1
      .locals init (int32 V_0)
      IL_0000:  ldc.i4.0
      IL_0001:  stloc.0
      IL_0002:  br.s       IL_0004

      IL_0004:  ldloc.0
      IL_0005:  ret
    } // end of method ReturnTypeTest::AMethod

    .method public hidebysig instance string
            AMethod(int32 x) cil managed
    {
      // Code size       10 (0xa)
      .maxstack  1
      .locals init (string V_0)
      IL_0000:  ldstr      "test"
      IL_0005:  stloc.0
      IL_0006:  br.s       IL_0008

      IL_0008:  ldloc.0
      IL_0009:  ret
    } // end of method ReturnTypeTest::AMethod

    .method public hidebysig specialname rtspecialname
            instance void  .ctor() cil managed
    {
      // Code size       7 (0x7)
      .maxstack  1
      IL_0000:  ldarg.0
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
      IL_0006:  ret
    } // end of method ReturnTypeTest::.ctor

  } // end of class ReturnTypeTest

} // end of namespace UsageLibrary

```



