---
title: 'CA1813: Vyhněte se nezapečetěným atributům | Dokumentace Microsoftu'
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
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: ee0b5ceb5a07f0f56f50e9566e14525a4f36835d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627380"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Vyhněte se nezapečetěným atributům
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1813: Vyhněte se nezapečetěným atributům](https://docs.microsoft.com/visualstudio/code-quality/ca1813-avoid-unsealed-attributes).  
  
TypeName | AvoidUnsealedAttributes |  
| ID kontroly | CA1813 |  
| Kategorie | Microsoft.Performance|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Veřejný typ dědí z <xref:System.Attribute?displayProperty=fullName>není abstraktní a není zapečetěná (`NotInheritable` v jazyce Visual Basic).  
  
## <a name="rule-description"></a>Popis pravidla  
 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Knihovny tříd poskytuje metody pro načítání vlastních atributů. Ve výchozím nastavení tyto metody prohledávají hierarchii dědičnosti atributů; například <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> vyhledá zadaného typu atributu nebo libovolný typ atributu, který rozšiřuje zadaného typu atributu. Zapečetění atributu eliminuje prohledávání hierarchie dědičnosti a může zlepšit výkon.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, zapečeťte typ atributu nebo vytvořit abstraktní.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění tohoto pravidla. Byste měli dělat jenom v případě, že definujete hierarchii atributů a nelze zapečetit atribut nebo vytvořit abstraktní.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje vlastní atribut, který splňuje toto pravidlo.  
  
 [!code-csharp[FxCop.Performance.AttributesSealed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/cs/FxCop.Performance.AttributesSealed.cs#1)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/vb/FxCop.Performance.AttributesSealed.vb#1)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1018: Označte atributy pomocí AttributeUsageAttribute](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](http://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)



