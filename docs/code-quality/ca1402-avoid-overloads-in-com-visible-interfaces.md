---
title: "CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9294e1aab07aa05bc10de507e0a5885a47ebcc40
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: Vyhněte se přetížení ve viditelných rozhraních modelu COM
|||  
|-|-|  
|TypeName|AvoidOverloadsInComVisibleInterfaces|  
|CheckId|CA1402|  
|Kategorie|Microsoft.Interoperability|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Modelu COM (Component Object) viditelné rozhraní deklaruje přetížený metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Když jsou přetížené metody vystaveny klientům modulu COM, zachová svůj název pouze první přetížení metody. Následné přetížení jsou jedinečně přejmenovat připojením k názvu znak podtržítkem '_' a celé číslo, které odpovídá pracovního prohlášení o přetížení. Zvažte například následující metody.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod(int valueOne, int valueTwo, int valueThree);  
void SomeMethod(int valueOne, int valueTwo);  
```  
  
 Tyto metody jsou viditelné na COM klientů jako následující.  
  
```  
void SomeMethod(int valueOne);  
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);  
void SomeMethod_3(int valueOne, int valueTwo);  
```  
  
 Klienti COM 6 Visual Basic nelze implementovat, metody rozhraní pomocí podtržítkem v názvu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, přejmenujte přetížené metody tak, aby byly jedinečné názvy. Můžete taky provést rozhraní neviditelná COM změnou usnadnění přístupu k `internal` (`Friend` v [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) nebo použitím <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> atribut nastaven na `false`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Nepotlačujte upozornění na toto pravidlo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje rozhraní, která porušuje pravidlo a rozhraní, které splňuje pravidlo.  
  
 [!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
 [!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]  
  
## <a name="related-rules"></a>Související pravidla  
 [CA1413: Vyhněte se neveřejným polím v hodnotách viditelných modulem COM](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)  
  
 [CA1407: Vyhněte se statickým členům ve viditelných typech modelu COM](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)  
  
 [CA1017: Označte sestavení pomocí atributu ComVisibleAttribute](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)  
  
## <a name="see-also"></a>Viz také  
 [Spolupráce s nespravovaným kódem](/dotnet/framework/interop/index)   
 [Datový typ Long](/dotnet/visual-basic/language-reference/data-types/long-data-type)