---
title: 'CA1041: Poskytněte zprávu ObsoleteAttribute | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dc851ef4b4ef1cdca9bdb1f9692d3bbc7f0a795c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
 <xref:System.ObsoleteAttribute> slouží k označení nepoužívané knihovny typů a členů. Příjemci knihovny musí Vyhněte se použití jakéhokoli typu nebo člena, který je označen jako zastaralý. To je, protože nemusí být podporován a nakonec se odebere z novější verze knihovny. Pokud typ nebo člen označené pomocí <xref:System.ObsoleteAttribute> zkompilován, <xref:System.ObsoleteAttribute.Message%2A> vlastnost atributu se zobrazí. To uživateli poskytuje informace o zastaralém typu nebo členu. Tyto informace zahrnují obecně jak dlouho zastaralý typ nebo člen bude podporovat Designer knihovny a upřednostňované nahrazení, můžete použít.  
  
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