---
title: "CA2112: Zabezpečené typy by neměly vystavovat pole | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d60784b92d414b6a226605cd406378c1686529dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Zabezpečené typy by neměly vystavovat pole
|||  
|-|-|  
|TypeName|SecuredTypesShouldNotExposeFields|  
|CheckId|CA2112|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ veřejné nebo chráněného obsahuje veřejná pole a zabezpečené [požadavky propojení](/dotnet/framework/misc/link-demands).  
  
## <a name="rule-description"></a>Popis pravidla  
 Pokud má kód přístup k instanci typu, která je zabezpečena pomocí požadavku na propojení, nemusí kód vyhovět požadavku na propojení pro přístup k polím tohoto typu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Chcete-li opravit porušení toto pravidlo, zkontrolujte pole neveřejní a přidejte veřejné vlastnosti nebo metody, které vrací pole data. Kontrola zabezpečení LinkDemand na typech chránit přístup k vlastnosti a metody typ. Zabezpečení přístupu kódu, ale nevztahuje na pole.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Pro problémy se zabezpečením i pro dobrý návrh by měl opravit porušení tím, že nonpublic veřejná pole. Upozornění od tohoto pravidla můžete potlačit, pokud toto pole neobsahuje informace, které by měla zůstat zabezpečené a jste nespoléhejte na obsah tohoto pole.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu se skládá z knihovny typů (`SecuredTypeWithFields`) s zabezpečená pole typu (`Distributor`), můžete vytvořit instanci typu knihovny chybné předává instance na typy nemáte oprávnění k jejich vytvoření a kódu aplikace, která pole instancí mohou přečíst, i když nemá oprávnění, které slouží k zabezpečení typu.  
  
 Následující kód knihovny porušuje pravidlo.  
  
 [!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]  
  
## <a name="example"></a>Příklad  
 Aplikaci nelze vytvořit instanci kvůli vyžádání odkaz, který chrání zabezpečené typu. Následující třídy umožňuje aplikaci získat instanci zabezpečené typu.  
  
 [!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace ukazuje, jak, bez oprávnění k přístupu k zabezpečeným typ metody, kód můžete přistupovat k jeho pole.  
  
 [!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Vytvoření instance SecuredTypeWithFields.**  
**Pole určující typ zabezpečené: 22, 33**  
**Změna zabezpečené typ pole...**  
**Pole objektů do mezipaměti: 99, 33**   
## <a name="related-rules"></a>Související pravidla  
 [CA1051: Nedeklarujte viditelná pole instance](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)  
  
## <a name="see-also"></a>Viz také  
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
 [Data a modelování](/dotnet/framework/data/index)