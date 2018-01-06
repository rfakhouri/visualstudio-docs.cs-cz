---
title: "CA2215: Metody Dispose by měly volat uvolnění třídy base | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 791de4f70113df3759e920591ec94da5108eec9a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 Chcete-li opravit porušení toto pravidlo, volejte `base`.<xref:System.IDisposable.Dispose%2A> ve vaší <xref:System.IDisposable.Dispose%2A> metoda.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, pokud volání `base`.<xref:System.IDisposable.Dispose%2A> dojde na podrobnější úrovni volání než pravidla kontroly.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ `TypeA` , která implementuje <xref:System.IDisposable>.  
  
 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../code-quality/codesnippet/CSharp/ca2215-dispose-methods-should-call-base-class-dispose_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ `TypeB` který dědí z typu `TypeA` a správně volá jeho <xref:System.IDisposable.Dispose%2A> metoda.  
  
 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../code-quality/codesnippet/VisualBasic/ca2215-dispose-methods-should-call-base-class-dispose_2.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IDisposable?displayProperty=fullName>   
 [Vzor pro metodu Dispose](/dotnet/standard/design-guidelines/dispose-pattern)