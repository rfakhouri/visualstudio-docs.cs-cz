---
title: 'CA1413: Vyhněte se neveřejným polím v viditelných typech modelu COM | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
helpviewer_keywords:
- CA1413
- AvoidNonpublicFieldsInComVisibleValueTypes
ms.assetid: 1352e7eb-fefc-4239-8847-25edc7804a54
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e68f29fed3a1f25eb2a80b1b6acf09827e8ee18f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1413-avoid-non-public-fields-in-com-visible-value-types"></a>CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM
|||  
|-|-|  
|TypeName|AvoidNonpublicFieldsInComVisibleValueTypes|  
|CheckId|CA1413|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ hodnoty, která je konkrétně označena jako viditelný na modelu COM (Component Object) deklaruje pole neveřejní instance.  
  
## <a name="rule-description"></a>Popis pravidla  
 Neveřejná pole instancí hodnotových typů viditelných moduly COM jsou viditelná klientům typu COM. Zkontrolujte obsah pole pro informace, které by neměly být vystaveny nebo která bude mít nechtěný efekt návrhu nebo zabezpečení.  
  
 Ve výchozím nastavení všechny veřejné hodnotové typy jsou viditelné pro COM. K snížil počet falešných poplachů, ale toto pravidlo vyžaduje COM viditelnost typ, který má být explicitně uvedena. Musí být označen obsahující sestavení <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> nastavena na `false` a typ musí být označené jako <xref:System.Runtime.InteropServices.ComVisibleAttribute> nastavena na `true`.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud chcete opravit porušení tohoto pravidla a ponechat pole skrytá, změňte typ hodnoty typu odkazu nebo odebrat <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut z typu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li veřejné ohrožení pole je přijatelná.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje typ, který porušuje pravidlo.  
  
 [!code-csharp[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/CSharp/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.cs)]
 [!code-vb[FxCop.Interoperability.NonpublicField#1](../code-quality/codesnippet/VisualBasic/ca1413-avoid-non-public-fields-in-com-visible-value-types_1.vb)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)   
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)