---
title: 'CA1018: Označte atributy pomocí AttributeUsageAttribute | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
helpviewer_keywords:
- CA1018
- MarkAttributesWithAttributeUsage
ms.assetid: 6ab70ec0-220f-4880-af31-45067703133c
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3d40b97ee7637b5f742caee71b23cd9d384a1ecc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1018-mark-attributes-with-attributeusageattribute"></a>CA1018: Označte atributy pomocí AttributeUsageAttribute
|||  
|-|-|  
|TypeName|MarkAttributesWithAttributeUsage|  
|CheckId|CA1018|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 <xref:System.AttributeUsageAttribute?displayProperty=fullName> Atribut není k dispozici pro vlastní atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když definujete vlastní atribut, označte ji pomocí <xref:System.AttributeUsageAttribute> označíte, kde ve zdrojovém kódu může být použito vlastních atributů. Význam a zamýšlené použití atributu určuje jeho platné umístění v kódu. Například můžete třeba definovat atribut, který identifikuje uživatele, který zodpovídá za údržbu a zlepšení jednotlivé typy v knihovně, a na úrovni typu se vždycky přiřazuje zodpovědnost. V takovém případě kompilátory měli povolit atribut na třídy, výčty a rozhraní, ale by neměla být povolena na metody, události nebo vlastnosti. Organizační zásady a postupy, by určují, zda má být povolen atribut sestavení.  
  
 <xref:System.AttributeTargets?displayProperty=fullName> Výčet definuje cíle, které můžete zadat pro vlastní atribut. Pokud vynecháte <xref:System.AttributeUsageAttribute>, vlastní atribut bude platit pro všechny cíle podle definice `All` hodnotu <xref:System.AttributeTargets> výčtu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, určete cíle pro atribut pomocí <xref:System.AttributeUsageAttribute>. Podívejte se na téma v následujícím příkladu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Problém byste měli odstranit narušení místo zprávu s výjimkou tohoto pravidla. I v případě, že atribut dědí <xref:System.AttributeUsageAttribute>, atribut by měl být k dispozici pro zjednodušení kód údržby.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu definuje dva atributy. `BadCodeMaintainerAttribute` nesprávně vynechá <xref:System.AttributeUsageAttribute> příkaz, a `GoodCodeMaintainerAttribute` správně implementuje atribut, který je popsán výše v této části. Všimněte si, že vlastnost `DeveloperName` je požadované pro pravidlo návrhu [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md) a je zahrnuté pro úplnost.  
  
 [!code-csharp[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/CSharp/ca1018-mark-attributes-with-attributeusageattribute_1.cs)]
 [!code-vb[FxCop.Design.AttributeUsage#1](../code-quality/codesnippet/VisualBasic/ca1018-mark-attributes-with-attributeusageattribute_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1019: Definujte přístupové objekty pro argumenty atributu](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)  
  
 [CA1813: Vyhněte se nezapečetěným atributům](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](/dotnet/standard/design-guidelines/attributes)