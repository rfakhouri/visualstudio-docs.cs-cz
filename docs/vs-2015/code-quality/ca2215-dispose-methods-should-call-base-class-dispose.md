---
title: 'CA2215: Metody Dispose by měly volat uvolnění základní třídy | Dokumentace Microsoftu'
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
- CA2215
- DisposeMethodsShouldCallBaseClassDispose
- Dispose methods should call base class dispose
helpviewer_keywords:
- DisposeMethodsShouldCallBaseClassDispose
- CA2215
ms.assetid: c772e7a6-a87e-425c-a70e-912664ae9042
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bacd16fa8c58fcbe6646e1b7c5f2a26fad8e4ce3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900981"
---
# <a name="ca2215-dispose-methods-should-call-base-class-dispose"></a>CA2215: Metody Dispose by měly volat uvolnění třídy Base
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2215: metody Dispose by měly volat uvolnění třídy base](https://docs.microsoft.com/visualstudio/code-quality/ca2215-dispose-methods-should-call-base-class-dispose).

|||
|-|-|
|TypeName|DisposeMethodsShouldCallBaseClassDispose|
|CheckId|CA2215|
|Kategorie|Microsoft.Usage|
|Narušující změna|Pevné|

## <a name="cause"></a>příčina
 Typ, který implementuje <xref:System.IDisposable?displayProperty=fullName> je odvozen z typu, který také implementuje <xref:System.IDisposable>. <xref:System.IDisposable.Dispose%2A> Nevolá metodu ze dědičné typu <xref:System.IDisposable.Dispose%2A> metoda nadřazeného typu.

## <a name="rule-description"></a>Popis pravidla
 Pokud typ dědí z uvolnitelného typu, musí volat <xref:System.IDisposable.Dispose%2A> metodu základního typu v rámci své vlastní <xref:System.IDisposable.Dispose%2A> metody. Volání metody základní typ Dispose zajistí, že se vydávají všechny prostředky vytvořené v rámci základního typu.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, zavolejte `base`.<xref:System.IDisposable.Dispose%2A> ve vaší <xref:System.IDisposable.Dispose%2A> metody.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Je bezpečné potlačit upozornění tohoto pravidla, pokud volání `base`.<xref:System.IDisposable.Dispose%2A> nastane na hlubší úrovni volání než pravidla kontroly.

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeA` , který implementuje <xref:System.IDisposable>.

 [!code-csharp[FxCop.Usage.IDisposablePattern#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposablePattern/cs/FxCop.Usage.IDisposablePattern.cs#1)]

## <a name="example"></a>Příklad
 Následující příklad ukazuje typ `TypeB` , která dědí z typu `TypeA` a správně volá jeho <xref:System.IDisposable.Dispose%2A> metoda.

 [!code-vb[FxCop.Usage.IDisposableBaseCalled#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.IDisposableBaseCalled/vb/FxCop.Usage.IDisposableBaseCalled.vb#1)]

## <a name="see-also"></a>Viz také
 <xref:System.IDisposable?displayProperty=fullName> [Vzor dispose](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



