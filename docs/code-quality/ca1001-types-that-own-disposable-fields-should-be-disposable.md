---
title: "CA1001: Typy, které vlastní uvolnitelné pole by měly být uvolnitelné | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
helpviewer_keywords:
- CA1001
- TypesThatOwnDisposableFieldsShouldBeDisposable
ms.assetid: c85c126c-2b16-4505-940a-b5ddf873fb22
caps.latest.revision: "22"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: dd2372acf82d275b0c240ee3fe1c17e687854340
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1001-types-that-own-disposable-fields-should-be-disposable"></a>CA1001: Typy, které vlastní uvolnitelné pole by měly být uvolnitelné
|||  
|-|-|  
|TypeName|TypesThatOwnDisposableFieldsShouldBeDisposable|  
|CheckId|CA1001|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Non narušující – Pokud typ není viditelná mimo sestavení.<br /><br /> Ukončování řádků – Pokud je typ viditelné mimo sestavení.|  
  
## <a name="cause"></a>příčina  
 Třída deklaruje a implementuje na pole instance, který je <xref:System.IDisposable?displayProperty=fullName> typu a třída neimplementuje <xref:System.IDisposable>.  
  
## <a name="rule-description"></a>Popis pravidla  
 Implementuje třídu <xref:System.IDisposable> rozhraní k uvolnění nespravovaných prostředků, které vlastní. Na pole instance, která je <xref:System.IDisposable> typ označuje, že pole vlastní nespravovaných prostředků. Třídy, který deklaruje <xref:System.IDisposable> pole nepřímo vlastní nespravovaný prostředek a měly by implementovat <xref:System.IDisposable> rozhraní. Pokud třída přímo nevlastní žádné nespravovaných prostředků, by neměly implementovat finalizační metody.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, implementujte <xref:System.IDisposable> a z <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> volání metody <xref:System.IDisposable.Dispose%2A> metoda pole.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje třídu, která porušuje pravidlo a třídu, která splňuje pravidlo implementací <xref:System.IDisposable>. Třída neimplementuje finalizační metody, protože třída přímo nevlastní žádné nespravovaných prostředků.  
  
 [!code-vb[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/VisualBasic/ca1001-types-that-own-disposable-fields-should-be-disposable_1.vb)]
 [!code-csharp[FxCop.Design.DisposableFields#1](../code-quality/codesnippet/CSharp/ca1001-types-that-own-disposable-fields-should-be-disposable_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2213: Uvolnitelné pole by mělo být uvolněno](../code-quality/ca2213-disposable-fields-should-be-disposed.md)  
  
 [CA2216: Uvolnitelné typy by měly deklarovat finalizační metodu](../code-quality/ca2216-disposable-types-should-declare-finalizer.md)  
  
 [CA2215: Metody Dispose by měly volat uvolnění třídy Base](../code-quality/ca2215-dispose-methods-should-call-base-class-dispose.md)  
  
 [CA1049: Typy, které vlastní nativní prostředky by měly být uvolnitelné](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)