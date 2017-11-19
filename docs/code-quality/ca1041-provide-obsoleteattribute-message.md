---
title: "CA1041: Poskytněte zprávu ObsoleteAttribute | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5d6c0ac4d5972e06768306be51a92e93da763ce0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: Poskytněte zprávu ObsoleteAttribute
|||  
|-|-|  
|TypeName|ProvideObsoleteAttributeMessage|  
|CheckId|CA1041|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Typ nebo člen je označena pomocí <xref:System.ObsoleteAttribute?displayProperty=fullName> atribut, který nemá jeho <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> zadanou vlastnost.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.ObsoleteAttribute>slouží k označení nepoužívané knihovny typů a členů. Příjemci knihovny musí Vyhněte se použití jakéhokoli typu nebo člena, který je označen jako zastaralý. To je, protože nemusí být podporován a nakonec se odebere z novější verze knihovny. Pokud typ nebo člen označené pomocí <xref:System.ObsoleteAttribute> zkompilován, <xref:System.ObsoleteAttribute.Message%2A> vlastnost atributu se zobrazí. To uživateli poskytuje informace o zastaralém typu nebo členu. Tyto informace zahrnují obecně jak dlouho zastaralý typ nebo člen bude podporovat Designer knihovny a upřednostňované nahrazení, můžete použít.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, přidejte `message` parametru <xref:System.ObsoleteAttribute> konstruktor.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Není potlačit upozornění na toto pravidlo, protože <xref:System.ObsoleteAttribute.Message%2A> vlastnost poskytuje důležité informace o zastaralé typ nebo člen.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje zastaralé člen, který má správně deklarované <xref:System.ObsoleteAttribute>.  
  
 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CPP/ca1041-provide-obsoleteattribute-message_1.cpp)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/CSharp/ca1041-provide-obsoleteattribute-message_1.cs)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../code-quality/codesnippet/VisualBasic/ca1041-provide-obsoleteattribute-message_1.vb)]  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ObsoleteAttribute?displayProperty=fullName>