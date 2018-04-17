---
title: 'CA2122: Nezveřejňují nepřímo metody s požadavky propojení | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 836fca663baaa5a5c62c720eac9f7408732f95d5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: Nezveřejňujte nepřímo metody s požadavky propojení
|||  
|-|-|  
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|  
|CheckId|CA2122|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Bez ukončování řádků|  
  
## <a name="cause"></a>příčina  
 Veřejné nebo chráněný člen má [požadavky propojení](/dotnet/framework/misc/link-demands) a volá člena, který neprovádí žádné kontroly zabezpečení.  
  
## <a name="rule-description"></a>Popis pravidla  
 Požadavek propojení kontroluje pouze oprávnění bezprostředního volajícího. Pokud člen `X` provádí žádné požadavky na zabezpečení svých volající a volání kód chráněné požadavkem propojení, volající bez nezbytná oprávnění můžete použít `X` přístup chráněného člena.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Přidat zabezpečení [Data a modelování](/dotnet/framework/data/index) nebo odkaz vyžádání člen tak, aby již poskytuje zabezpečená přístup na vyžádání chráněného člena odkaz.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Bezpečně potlačit upozornění na toto pravidlo, ujistěte se, že váš kód neposkytuje jeho volající přístup k operace nebo prostředky, které můžete použít destruktivní způsobem.  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují knihovnu, která porušuje pravidlo a aplikace, která demonstruje slabé místo na knihovně. Ukázka knihovna nabízí dvě metody, které společně porušují pravidlo. `EnvironmentSetting` Metoda je zabezpečená službou požadavek propojení pro neomezený přístup k proměnné prostředí. `DomainInformation` Metoda provádí žádné požadavky na zabezpečení volajících zavolá `EnvironmentSetting`.  
  
 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace volá člen zabezpečená knihovny.  
  
 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Hodnota z nezabezpečená člena: seattle.corp.contoso.com**   
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
 [Data a modelování](/dotnet/framework/data/index)