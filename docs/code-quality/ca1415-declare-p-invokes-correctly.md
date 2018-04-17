---
title: 'CA1415: Deklarujte vyvolá P správně | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1415
- DeclarePInvokesCorrectly
helpviewer_keywords:
- CA1415
- DeclarePInvokesCorrectly
ms.assetid: 42a90796-0264-4460-bf97-2fb4a093dfdc
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bfad5d5a699fda54c91e674365b65305ef7fad0d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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