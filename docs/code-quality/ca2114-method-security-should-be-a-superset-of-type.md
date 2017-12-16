---
title: "CA2114: Zabezpečení metody by měla být nadmnožinou typu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MethodSecurityShouldBeASupersetOfType
- CA2114
helpviewer_keywords:
- CA2114
- MethodSecurityShouldBeASupersetOfType
ms.assetid: 663f7aa4-8be5-4bd5-be92-4e9444f07077
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ac633134b5b8037eb9e45131128b0ee0cf2887ab
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="ca2114-method-security-should-be-a-superset-of-type"></a>CA2114: Zabezpečení metody by mělo být nadmnožinou typu
|||  
|-|-|  
|TypeName|MethodSecurityShouldBeASupersetOfType|  
|CheckId|CA2114|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Typ má deklarativní zabezpečení a jeden z jeho metody má deklarativní zabezpečení pro stejnou akci zabezpečení a zabezpečení akce není [požadavky propojení](/dotnet/framework/misc/link-demands), a zkontrolovat nástrojem typ oprávnění nejsou podmnožinu oprávnění ověří pomocí metody.  
  
## <a name="rule-description"></a>Popis pravidla  
 Metody by neměla mít jak metoda úroveň a typ deklarativní zabezpečení pro stejnou akci. Dva kontroly se nekombinují; je použita pouze vyžádání úrovni metody. Například, pokud typ požaduje oprávnění `X`, a jeden z jeho metody požaduje oprávnění `Y`, kód nemá oprávnění k `X` provést metodu.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Zkontrolujte kód a ujistěte se, že obě akce jsou povinné. Pokud jsou požadovány obě akce, ujistěte se, že úrovni metody akce obsahuje zabezpečení zadané pro úroveň typu. Například, pokud typ vašeho požaduje oprávnění `X`, a jeho metoda musí také požadovat oprávnění `Y`, metoda by měla explicitně požadovat `X` a `Y`.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Je bezpečné potlačit upozornění na toto pravidlo, je-li metoda nevyžaduje zabezpečení určeného typu. To však není běžné scénáře a může znamenat potřebu kontrolu pečlivě návrhu.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá prostředí oprávnění k předvedení nebezpečích bychom při tom porušili toto pravidlo. V tomto příkladu kódu aplikace vytvoří instanci typu zabezpečené před odepřením oprávnění požadované podle typu. Ve scénáři skutečné hrozby by aplikace vyžadují jiný způsob, jak získat instanci objektu.  
  
 V následujícím příkladu požadavky knihovny oprávnění pro typ zapisovat a oprávnění ke čtení pro metodu.  
  
 [!code-csharp[FxCop.Security.MethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující kód aplikace ukazuje ohrožení zabezpečení knihovny voláním metody, i když nesplňuje požadavek na zabezpečení na úrovni typu.  
  
 [!code-csharp[FxCop.Security.TestMethodLevelSecurity#1](../code-quality/codesnippet/CSharp/ca2114-method-security-should-be-a-superset-of-type_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **[Všechna oprávnění] Osobní údaje: 6/16/1964 12:00:00: 00**  
**[Žádné oprávnění k zápisu (pro název typu)] Osobní údaje: 6/16/1964 12:00:00: 00**  
**[Žádné oprávnění ke čtení (pro název metoda)] Nelze získat přístup k osobním údajům: žádost se nezdařila.**   
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
 [Data a modelování](/dotnet/framework/data/index)