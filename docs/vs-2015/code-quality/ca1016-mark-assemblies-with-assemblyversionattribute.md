---
title: 'CA1016: Označte sestavení pomocí atributu AssemblyVersionAttribute | Dokumentace Microsoftu'
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
- MarkAssembliesWithAssemblyVersion
- CA1016
helpviewer_keywords:
- CA1016
- MarkAssembliesWithAssemblyVersion
ms.assetid: 4340aed8-d92b-4cde-a398-cb6963c6da5a
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 0aa904cb8155323c4fee86ca7c32504ac0d8667d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672727"
---
# <a name="ca1016-mark-assemblies-with-assemblyversionattribute"></a>CA1016: Označte sestavení pomocí atributu AssemblyVersionAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1016: označte sestavení pomocí atributu AssemblyVersionAttribute](https://docs.microsoft.com/visualstudio/code-quality/ca1016-mark-assemblies-with-assemblyversionattribute).  
  
TypeName | MarkAssembliesWithAssemblyVersion |  
| ID kontroly | CA1016 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Sestavení nemá číslo verze.  
  
## <a name="rule-description"></a>Popis pravidla  
 Identita sestavení se skládá z následujících informací:  
  
-   Název sestavení  
  
-   Číslo verze  
  
-   Jazyková verze  
  
-   Veřejný klíč (pro sestavení se silným názvem).  
  
 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Používá číslo verze k jednoznačné identifikaci sestavení a pro svázání s typy v sestaveních se silným názvem. Číslo verze je používáno spolu se zásadou verze a vydavatele. Ve výchozím nastavení mohou být aplikace spuštěny pouze ve verzi sestavení, v níž byly sestaveny.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přidejte číslo verze na sestavení s použitím <xref:System.Reflection.AssemblyVersionAttribute?displayProperty=fullName> atribut. Podívejte se na téma v následujícím příkladu.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění tohoto pravidla pro sestavení, které jsou používány třetími stranami, nebo v produkčním prostředí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje sestavení, který má <xref:System.Reflection.AssemblyVersionAttribute> atribut.  
  
 [!code-cpp[FxCop.Design.AssembliesVersion#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/cpp/FxCop.Design.AssembliesVersion.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesVersion#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/cs/FxCop.Design.AssembliesVersion.cs#1)]
 [!code-vb[FxCop.Design.AssembliesVersion#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesVersion/vb/FxCop.Design.AssembliesVersion.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Správa verzí sestavení](http://msdn.microsoft.com/library/775ad4fb-914f-453c-98ef-ce1089b6f903)   
 [Postupy: Vytváření zásad vydavatele](http://msdn.microsoft.com/library/8046bc5d-2fa9-4277-8a5e-6dcc96c281d9)



