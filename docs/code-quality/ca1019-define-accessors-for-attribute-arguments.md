---
title: "CA1019: Definujte přístupové objekty pro argumenty atributu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9f04a49c8c68fcc597ecd98471b46932d467b365
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: Definujte přístupové objekty pro argumenty atributu
|||  
|-|-|  
|TypeName|DefineAccessorsForAttributeArguments|  
|CheckId|CA1019|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 V jeho konstruktoru definuje atribut argumenty, které nemají odpovídající vlastnosti.  
  
## <a name="rule-description"></a>Popis pravidla  
 Atributy mohou definovat povinné argumenty, které musí být specifikovány při použití atributu na cíl. Říká se jim také poziční argumenty, jelikož jsou konstruktorům atributů předány jako poziční parametry. Pro každý povinný argument by měl atribut navíc poskytovat odpovídající vlastnost jen pro čtení, aby mohla být hodnota argumentu během spuštění získána. Toto pravidlo zkontroluje, že pro každý parametr konstruktoru jste definovali odpovídající vlastnost.  
  
 Atributy mohou také definovat volitelné argumenty, které jsou rovněž známy jako pojmenované argumenty. Tyto argumenty jsou podle názvu poskytovány konstruktorům atributů a měly by mít odpovídající vlastnost pro čtení i zápis.  
  
 Povinné a nepovinné argumenty, odpovídající vlastnosti a konstruktor parametrů by měl použijte stejný název ale odlišným velká a malá písmena. Vlastnosti použít Pascal velká a malá písmena a parametry použití formátu camelCase velká a malá písmena.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidání vlastnosti jen pro čtení pro každý parametr konstruktoru, který nemá.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo, pokud nechcete, aby hodnota bude nenávratně argument povinný.  
  
## <a name="custom-attributes-example"></a>Příklad vlastní atributy  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje dva atributy, které definují povinný parametr (poziční). První implementace atributu je definována nesprávně. Druhý implementace je správná.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
 [!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]  
  
## <a name="positional-and-named-arguments"></a>Poziční a pojmenované argumenty  
  
### <a name="description"></a>Popis  
 Poziční a pojmenované argumenty proveďte vymazat k příjemce své knihovny, které argumenty jsou povinné pro atribut a které argumenty jsou volitelné.  
  
 Následující příklad ukazuje implementaci pro atribut, který má poziční a pojmenované argumenty.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]  
  
### <a name="comments"></a>Komentáře  
 Následující příklad ukazuje, jak chcete použít vlastní atribut pro dvě vlastnosti.  
  
### <a name="code"></a>Kód  
 [!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1813: Vyhněte se nezapečetěným atributům](../code-quality/ca1813-avoid-unsealed-attributes.md)  
  
## <a name="see-also"></a>Viz také  
 [Atributy](/dotnet/standard/design-guidelines/attributes)