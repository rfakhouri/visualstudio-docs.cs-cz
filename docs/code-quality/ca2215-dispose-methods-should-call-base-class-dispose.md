---
title: 'CA2215: Metody Dispose by měly volat uvolnění třídy base | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d8eb5c56ab3affe6322a858dfcd34c3b138f26d7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Metody Dispose by měly volat uvolnění třídy Base
|||  
|-|-|  
|TypeName|DisposeMethodsShouldCallBaseClassDispose|  
|CheckId|CA2215|  
|Kategorie|Microsoft.Usage|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> dědí od typu, který také implementuje <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Metoda dědičných typu nevyvolá <xref:System.IDisposable.Dispose%2A> metoda nadřazeného typu.  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud typ dědí od typu na jedno použití, musí volat <xref:System.IDisposable.Dispose%2A> metoda základní typu v rámci vlastní <xref:System.IDisposable.Dispose%2A> metoda. Volání metody základní typ uvolnění zajišťuje, vydání všechny prostředky vytvořené základního typu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, volejte `base`.<xref:System.IDisposable.Dispose%2A> ve vašem <xref:System.IDisposable.Dispose%2A> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud volání `base`.<xref:System.IDisposable.Dispose%2A> dojde k na podrobnější úrovni volání než pravidla kontroly.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ `TypeA` , která implementuje <xref:System.IDisposable>.  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ `TypeB` který dědí z typu `TypeA` a správně volá jeho <xref:System.IDisposable.Dispose%2A> metoda.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)