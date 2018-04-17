---
title: 'CA1816: Volejte GC. Funkce SuppressFinalize správně | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1816
- DisposeMethodsShouldCallSuppressFinalize
helpviewer_keywords:
- DisposeMethodsShouldCallSuppressFinalize
- CA1816
ms.assetid: 47915fbb-103f-4333-b157-1da16bf49660
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d6d65561e9b902202d4fc69d15d200482880cf4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1816-call-gcsuppressfinalize-correctly"></a>CA1816: Volejte správně GC.SuppressFinalize
|||  
|-|-|  
|TypeName|CallGCSuppressFinalizeCorrectly|  
|CheckId|CA1816|  
|Kategorie|Společnosti Microsoft. Použití|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
  
-   Metoda, která je implementací <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> nevyvolá <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Metoda, která není implementace <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
-   Volá metodu <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> a předá něco jiného než tento (Me v jazyce Visual Basic).  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> Metoda umožňuje uživatelům uvolnění prostředků kdykoli před objekt stává stále k dispozici pro uvolňování paměti. Pokud <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> metoda je volána, se uvolní prostředky objektu. Díky tomu finalizace zbytečné. <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> měla by volat <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> , bude systém uvolňování nevyvolá finalizační metodu objektu.  
  
 K tomu, aby odvozené typy s finalizační metody k implementaci znovu <xref:System.IDisposable> a pokud chcete ji zavolat, by měly volat stále nezapečetěné typy bez finalizační metody <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo:  
  
 Pokud metoda je implementací <xref:System.IDisposable.Dispose%2A>, že přidáte volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 Pokud metoda není implementace <xref:System.IDisposable.Dispose%2A>, buď odeberte volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> nebo ho přesunout na typ <xref:System.IDisposable.Dispose%2A> implementace.  
  
 Změnit všechna volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> předat tuto (Me v jazyce Visual Basic).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pouze potlačit upozornění na toto pravidlo, pokud jsou deliberating pomocí <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName> k řízení životního cyklu jiných objektů. Není potlačit upozornění na toto pravidlo, pokud implementace <xref:System.IDisposable.Dispose%2A> nevyvolá <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>. V této situaci se nedaří potlačit finalizace snižuje výkon a poskytovat žádné výhody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která nesprávně volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_1.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje metodu, která správně volání <xref:System.GC.SuppressFinalize%2A?displayProperty=fullName>.  
  
 [!code-vb[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/VisualBasic/ca1816-call-gc-suppressfinalize-correctly_2.vb)]
 [!code-csharp[FxCop.Usage.CallGCSuppressFinalizeCorrectly2#1](../code-quality/codesnippet/CSharp/ca1816-call-gc-suppressfinalize-correctly_2.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2215: Metody Dispose by měly volat uvolnění třídy Base](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
## <a name="see-also"></a>Viz také  
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)