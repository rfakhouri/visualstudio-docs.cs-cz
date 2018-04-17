---
title: 'CA2220: Finalizační metody by měly volat finalizační metodu třídy base | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
helpviewer_keywords:
- CA2220
- FinalizersShouldCallBaseClassFinalizer
ms.assetid: 48329f42-170d-45ee-a381-e33f55a240c5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3b2d5181e04a9a44516716ff280802eb5232f8da
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2220-finalizers-should-call-base-class-finalizer"></a>CA2220: Finalizační metody by měly volat finalizační metodu třídy Base
|||  
|-|-|  
|TypeName|FinalizersShouldCallBaseClassFinalizer|  
|CheckId|CA2220|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ, který přepíše <xref:System.Object.Finalize%2A?displayProperty=fullName> nevyvolá <xref:System.Object.Finalize%2A> metoda v její základní třída.  
  
## <a name="rule-description"></a>Popis pravidla  
 Finalizační metoda musí být šířena přes hierarchii dědičnosti. Aby, musí volat typy jejich základní třídy <xref:System.Object.Finalize%2A> metoda z v rámci své vlastní <xref:System.Object.Finalize%2A> metoda. Kompilátor jazyka C# automaticky přidá volání finalizační metodu třídy base.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, volejte základní typ <xref:System.Object.Finalize%2A> metoda z vaší <xref:System.Object.Finalize%2A> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Některé kompilátory, které cílí modul common language runtime vložit volání finalizační metodu základní typ do Microsoft (MSIL intermediate language). Pokud upozornění na toto pravidlo se použije v hlášení, vaše kompilátoru nevkládá volání a je třeba přidat ji do vašeho kódu.  
  
## <a name="example"></a>Příklad  
 Následující příklad jazyka Visual Basic ukazuje typ `TypeB` , správně volá <xref:System.Object.Finalize%2A> metoda v její základní třída.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2220-finalizers-should-call-base-class-finalizer_1.vb)]  
  
## <a name="see-also"></a>Viz také  
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)