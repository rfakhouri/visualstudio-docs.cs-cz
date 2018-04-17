---
title: 'CA2221: Finalizační metody by měly chráněné. | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1e5e761339b34cab1f00bc2f5b4db28a51ef3193
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221: Finalizační metody by měly být chráněné
|||  
|-|-|  
|TypeName|FinalizersShouldBeProtected|  
|CheckId|CA2221|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Veřejného typu implementuje finalizační metodu, která neurčuje rodiny (chráněné) přístup.  
  
## <a name="rule-description"></a>Popis pravidla  
 Finalizační metody musí použít modifikátor přístupu family. Toto pravidlo se vynucuje kompilátory jazyka C#, Visual Basic a Visual C++.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, změňte finalizační metodu rodiny přístupné.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Toto pravidlo nemůže být došlo k porušení v kterémkoli jazyce platformy .NET vysoké úrovně; může být narušena, pokud píšete Microsoft Intermediate Language.  
  
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
  
## <a name="see-also"></a>Viz také  
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)