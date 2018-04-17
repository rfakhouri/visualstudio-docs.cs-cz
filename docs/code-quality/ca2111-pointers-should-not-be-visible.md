---
title: 'CA2111: Ukazatelé by neměli být viditelné | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- PointersShouldNotBeVisible
- CA2111
helpviewer_keywords:
- CA2111
- PointersShouldNotBeVisible
ms.assetid: b3a8d466-895b-43bc-a2df-5d7058fe915f
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ce027b8e6bcf39623e07a862d4f9fb23c33b9967
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2111-pointers-should-not-be-visible"></a>CA2111: Ukazatelé by neměli být viditelné
|||  
|-|-|  
|TypeName|PointersShouldNotBeVisible|  
|CheckId|CA2111|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 A veřejné nebo chráněného <xref:System.IntPtr?displayProperty=fullName> nebo <xref:System.UIntPtr?displayProperty=fullName> pole není jen pro čtení.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.IntPtr> a <xref:System.UIntPtr> jsou typy ukazatelů, které se používají pro přístup k nespravované paměti. Pokud není ukazatel privátní, interní nebo jen pro čtení, můžete změnit škodlivý kód hodnota ukazatele, potenciálně povolit přístup k libovolného umístění v paměti nebo způsobuje selhání aplikace nebo systému.  
  
 Pokud máte v úmyslu zabezpečený přístup k typ, který obsahuje pole ukazatele, přečtěte si téma [CA2112: zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md).  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Tím, že ji jen pro čtení, interní nebo privátní Zabezpečte ukazatele.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění od tohoto pravidla, pokud jste nespoléhejte na základě hodnoty ukazatele.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje ukazatele, které porušují a splňovat pravidla. Všimněte si, ne privátní ukazatele také porušují pravidlo [CA1051: nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md).  
  
 [!code-csharp[FxCop.Security.PointersArePrivate#1](../code-quality/codesnippet/CSharp/ca2111-pointers-should-not-be-visible_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA2112: Zabezpečené typy by neměly vystavovat pole](../code-quality/ca2112-secured-types-should-not-expose-fields.md)  
  
 [CA1051: Nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Viz také  
 <xref:System.IntPtr?displayProperty=fullName>   
 <xref:System.UIntPtr?displayProperty=fullName>