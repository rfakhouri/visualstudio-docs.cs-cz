---
title: 'CA1017: Označte sestavení pomocí atributu ComVisibleAttribute | Dokumentace Microsoftu'
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
- CA1017
- MarkAssembliesWithComVisible
helpviewer_keywords:
- MarkAssembliesWithComVisible
- CA1017
ms.assetid: 4842cb49-8dd8-4e5d-a2d6-ceeaf6c6cf8e
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7e6ed67cd3b849421e82a7ac2fb83d546d1f2d26
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633127"
---
# <a name="ca1017-mark-assemblies-with-comvisibleattribute"></a>CA1017: Označte sestavení pomocí atributu ComVisibleAttribute
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA1017: označte sestavení pomocí atributu ComVisibleAttribute](https://docs.microsoft.com/visualstudio/code-quality/ca1017-mark-assemblies-with-comvisibleattribute).  
  
TypeName | MarkAssembliesWithComVisible |  
| ID kontroly | CA1017 |  
| Kategorie | Microsoft.Design|  
| Zásadní změna | Ukončování bez |  
  
## <a name="cause"></a>příčina  
 Sestavení nemá <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> byt aplikovaný atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Atribut určuje způsob přístupu klientů COM ke spravovanému kódu. Dobrý návrh přikazuje, aby sestavení explicitně uvedla viditelnost modelu COM. Viditelnost modelu COM lze nastavit pro celé sestavení a poté přepsána pro jednotlivé typy a členy typu. Pokud atribut neexistuje, je obsah sestavení viditelný klientům com.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení tohoto pravidla, přidejte atribut do sestavení. Pokud nechcete, aby sestavení viditelný klientům modelu COM, použijte atribut a nastavte jej na hodnotu `false`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo. Pokud chcete sestavení viditelný, použijte atribut a nastavte jej na hodnotu `true`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje sestavení, který má <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut tak, aby se pro klienty modelu COM viditelný.  
  
 [!code-cpp[FxCop.Design.AssembliesCom#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cpp/FxCop.Design.AssembliesCom.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCom#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/cs/FxCop.Design.AssembliesCom.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCom#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCom/vb/FxCop.Design.AssembliesCom.vb#1)]  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)   
 [Kvalifikace typů .NET pro spolupráci](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)



