---
title: 'CA1016: Označte sestavení pomocí atributu AssemblyVersionAttribute'
ms.date: 11/04/2016
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6c4f05003fdd05a4dde82d19ba11e47c35666fbc
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: Označte sestavení pomocí atributu AssemblyVersionAttribute
|||
|-|-|
|TypeName|MarkAssembliesWithAssemblyVersion|
|CheckId|CA1016|
|Kategorie|Microsoft.Design|
|Narušující změna|Nenarušující|

## <a name="cause"></a>příčina
 Sestavení nemá číslo verze.

## <a name="rule-description"></a>Popis pravidla
 Identita sestavení se skládá z následujících informací:

-   Název sestavení

-   Číslo verze

-   Jazyková verze

-   Veřejný klíč (pro sestavení se silným názvem).

 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] k jednoznačné identifikaci sestavení a vytvoření vazby na typy v sestavení se silným názvem používá číslo verze. Číslo verze je používáno spolu se zásadou verze a vydavatele. Ve výchozím nastavení mohou být aplikace spuštěny pouze ve verzi sestavení, v níž byly sestaveny.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení
 Chcete-li opravit porušení toto pravidlo, přidat číslo verze sestavení pomocí <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> atribut. Podívejte se na téma v následujícím příkladu.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění
 Upozornění z toto pravidlo potlačit není pro sestavení, které se používají třetích stran nebo v provozním prostředí.

## <a name="example"></a>Příklad
 Následující příklad ukazuje, sestavení, který má <xref:System.Reflection.AssemblyVersionAttribute> atribut použitý.

 [!code-csharp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CSharp/ca1016-mark-assemblies-with-assemblyversionattribute_1.cs)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/VisualBasic/ca1016-mark-assemblies-with-assemblyversionattribute_1.vb)]
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../code-quality/codesnippet/CPP/ca1016-mark-assemblies-with-assemblyversionattribute_1.cpp)]

## <a name="see-also"></a>Viz také
 [Správa verzí sestavení](/dotnet/framework/app-domains/assembly-versioning) [postupy: vytváření zásad vydavatele](/dotnet/framework/configure-apps/how-to-create-a-publisher-policy)