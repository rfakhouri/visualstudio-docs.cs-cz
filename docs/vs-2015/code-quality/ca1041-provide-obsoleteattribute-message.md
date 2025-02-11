---
title: 'CA1041: Poskytněte zprávu ObsoleteAttribute | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1041
- ProvideObsoleteAttributeMessage
helpviewer_keywords:
- ProvideObsoleteAttributeMessage
- CA1041
ms.assetid: be5bee69-d2d2-44e1-be2e-3ea451969003
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: fe14ca0c0e917896a2ed5a31a03a8c1a7057d613
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62559825"
---
# <a name="ca1041-provide-obsoleteattribute-message"></a>CA1041: Poskytněte zprávu ObsoleteAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

|||
|-|-|
|TypeName|ProvideObsoleteAttributeMessage|
|CheckId|CA1041|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>Příčina
 Typ nebo člen je označen pomocí <xref:System.ObsoleteAttribute?displayProperty=fullName> atribut, který nemá jeho <xref:System.ObsoleteAttribute.Message%2A?displayProperty=fullName> zadanou vlastnost.

## <a name="rule-description"></a>Popis pravidla
 <xref:System.ObsoleteAttribute> slouží k označení nepoužívané knihovny typů a členů. Příjemci knihovny se měli vyhnout použití jakéhokoli typu nebo člena, který je označen jako zastaralý. Toto je vzhledem k tomu, že nemusí být podporován a nakonec se odebere z novější verze knihovny. Když typ nebo člen označen pomocí <xref:System.ObsoleteAttribute> kompilaci, <xref:System.ObsoleteAttribute.Message%2A> vlastnost atributu se zobrazí. To uživateli poskytuje informace o zastaralém typu nebo členu. Tyto informace obecně zahrnuje jak dlouho zastaralý typ nebo člen bude podporovat knihovny návrhářů a upřednostňovaný nahrazení použít.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení tohoto pravidla, přidejte `message` parametr <xref:System.ObsoleteAttribute> konstruktoru.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Nepotlačujte upozornění tohoto pravidla, protože <xref:System.ObsoleteAttribute.Message%2A> vlastnost poskytuje důležité informace o zastaralý typ nebo člen.

## <a name="example"></a>Příklad
 Následující příklad ukazuje zastaralý člen, který má správně deklarované <xref:System.ObsoleteAttribute>.

 [!code-cpp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cpp/FxCop.Design.ObsoleteAttributeOnMember.cpp#1)]
 [!code-csharp[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/cs/FxCop.Design.ObsoleteAttributeOnMember.cs#1)]
 [!code-vb[FxCop.Design.ObsoleteAttributeOnMember#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ObsoleteAttributeOnMember/vb/FxCop.Design.ObsoleteAttributeOnMember.vb#1)]

## <a name="see-also"></a>Viz také
 <xref:System.ObsoleteAttribute?displayProperty=fullName>
