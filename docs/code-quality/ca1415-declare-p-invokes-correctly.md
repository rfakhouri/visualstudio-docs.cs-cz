---
title: "CA1415: Deklarujte vyvolá P správně | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: b1bacff8f97a27a02ccdf8e6f6047bfd6ad9c90b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1415-declare-pinvokes-correctly"></a>CA1415: Deklarujte správně volání nespravovaných kódů
|||  
|-|-|  
|TypeName|DeclarePInvokesCorrectly|  
|CheckId|CA1415|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Non narušující – Pokud P/Invoke, který deklaruje parametr je nemohou vidět mimo sestavení. Rozdělení - P/Invoke, který deklaruje parametr si můžete prohlédnout mimo sestavení.|  
  
## <a name="cause"></a>příčina  
 Platforma vyvolání metody je nesprávně deklarován.  
  
## <a name="rule-description"></a>Popis pravidla  
 Platforma volání nespravovaného kódu metoda přístupů a je definován pomocí `Declare` – klíčové slovo v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. V současné době toto pravidlo vyhledá metoda deklarace, které cílí Win32 funkce, které mají ukazatel na strukturu parametru OVERLAPPED vyvolání platformy a odpovídající spravované parametr není ukazatel na <xref:System.Threading.NativeOverlapped?displayProperty=fullName> struktury.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, správně deklarovat platformou vyvolat metodu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje vyvolání metod, které porušují pravidlo a splňovat pravidla platformy.  
  
 [!code-csharp[FxCop.Interoperability.DeclarePInvokes#1](../code-quality/codesnippet/CSharp/ca1415-declare-p-invokes-correctly_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)