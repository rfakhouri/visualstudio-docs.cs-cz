---
title: 'CA1017: Označte sestavení pomocí atributu ComVisibleAttribute | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5aa835d06dc081445673bc3a92dff1184d329d51
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Označte sestavení pomocí atributu ComVisibleAttribute
|||  
|-|-|  
|TypeName|MarkAssembliesWithComVisible|  
|CheckId|CA1017|  
|Kategorie|Microsoft.Design|  
|Narušující změna|Nenarušující|  
  
## <a name="cause"></a>příčina  
 Sestavení nemá <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> byt aplikovaný atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Atribut určuje, jak klienti COM přístup spravovaného kódu. Dobrý návrh přikazuje, aby sestavení explicitně uvedla viditelnost modelu COM. Viditelnost COM můžete nastavit pro celé sestavení a pak pro jednotlivé typy a členy typu přepsána. Pokud atribut neexistuje, obsah sestavení jsou viditelné modelu COM klientů.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Opravit porušení toto pravidlo, přidejte atribut sestavení. Pokud nechcete, aby sestavení, které má být viditelné modelu COM klientů, použijte atribut a jeho hodnotu nastavte `false`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Pokud chcete sestavení, které má být viditelná, použijte atribut a jeho hodnotu nastavte `true`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, sestavení, který má <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut použitý brání jeho viditelné modelu COM klientům.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CPP/ca1017-mark-assemblies-with-comvisibleattribute_1.cpp)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/VisualBasic/ca1017-mark-assemblies-with-comvisibleattribute_1.vb)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../code-quality/codesnippet/CSharp/ca1017-mark-assemblies-with-comvisibleattribute_1.cs)]  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)   
 [Kvalifikace typů .NET pro spolupráci](/dotnet/framework/interop/qualifying-net-types-for-interoperation)