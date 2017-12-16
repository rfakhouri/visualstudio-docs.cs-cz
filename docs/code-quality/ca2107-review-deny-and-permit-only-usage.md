---
title: "CA2107: Zkontrolujte použití Odepřít a povolit pouze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA2107
- ReviewDenyAndPermitOnlyUsage
helpviewer_keywords:
- ReviewDenyAndPermitOnlyUsage
- CA2107
ms.assetid: 366f4a56-ae93-4882-81d0-bd0a55ebbc26
caps.latest.revision: "19"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: edd0bd14a75dfd58ca043bfaa663e2cfb2660e75
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="ca2107-review-deny-and-permit-only-usage"></a>CA2107: Revize použití operací odepřít a povolit pouze
|||  
|-|-|  
|TypeName|ReviewDenyAndPermitOnlyUsage|  
|CheckId|CA2107|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda obsahuje kontrolu zabezpečení, která určuje akce zabezpečení PermitOnly nebo odepřít.  
  
## <a name="rule-description"></a>Popis pravidla  
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName> Zabezpečení akce má být používána pouze ty, kteří mají pokročilé znalosti o [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] zabezpečení. Kód používající tyto bezpečnostní akce by měl být podroben revizi zabezpečení.  
  
 Odepřít mění výchozí chování, k níž dojde v reakci na poptávku zabezpečení procházení zásobníku. Umožňuje vám určit oprávnění, která nesmí po dobu trvání metodu odmítá, bez ohledu na skutečná oprávnění volajících v zásobníku volání. Pokud procházení zásobníku zjistí metodu, která je zabezpečená službou Odepřít a pokud požadované oprávnění je součástí odepřených oprávnění, procházení zásobníku se nezdaří. PermitOnly také mění výchozí chování procházení zásobníku. To umožňuje kódu k určení jenom oprávnění, které lze udělit, bez ohledu na oprávnění volající. Pokud procházení zásobníku zjistí metodu, která je zabezpečená službou PermitOnly, a pokud požadované oprávnění nezahrnuje oprávnění, které jsou určené PermitOnly, procházení zásobníku se nezdaří.  
  
 Kód, který závisí na těchto akcí je třeba pečlivě zvážit pro chyby zabezpečení z důvodu jejich omezené užitečnost a jemně chování. Zvažte následující:  
  
-   [Požadavky na propojení](/dotnet/framework/misc/link-demands) nemá vliv odepřít nebo PermitOnly.  
  
-   Pokud odepřít nebo PermitOnly dojde v rámci zásobníku jako požadavek, který způsobuje, že procházení zásobníku, akce zabezpečení nemají žádný vliv.  
  
-   Hodnoty, které se používají k vytvoření oprávnění na základě cesty lze obvykle několika způsoby. Odepření přístupu pro jednu formu cesty není odepřít přístup všem formulářům. Například, pokud sdílenou složku \\\Server\Share je namapovaná na síťové jednotce X: tak, aby odepřel přístup k souboru ve sdílené složce, musíte zakázat \\\Server\Share\File, X:\File a každé jiné cesty, který má přístup k souboru.  
  
-   <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> Před dosažením odepřít nebo PermitOnly můžete ukončit procházení zásobníku.  
  
-   Pokud odepření nemá žádný vliv, a to, pokud má volající oprávnění, která je blokována odepřít, volající přístup k chráněnému prostředku přímo, obcházení zamítnout. Podobně pokud má volající nemá oprávnění k odepření, procházení zásobníku selže bez zamítnout.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Jakékoli použití tyto zabezpečení akce způsobí, že porušení. Pokud chcete vyřešit narušení, nepoužívejte tyto akce zabezpečení.  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Potlačíte upozornění na toto pravidlo až po dokončení kontrolu zabezpečení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje určitá omezení Odepřít.  
  
 Následující knihovna obsahuje třídy, která má dvě metody, které jsou stejné s výjimkou požadavky zabezpečení, které je chránit.  
  
 [!code-csharp[FxCop.Security.PermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_1.cs)]  
  
## <a name="example"></a>Příklad  
 Následující aplikace ukazuje účinky odepřít na zabezpečené metody z knihovny.  
  
 [!code-csharp[FxCop.Security.TestPermitAndDeny#1](../code-quality/codesnippet/CSharp/ca2107-review-deny-and-permit-only-usage_2.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Vyžádání: Volajícího odepřít nemá žádný vliv na vyžádání s uplatňovaná oprávnění.**  
**LinkDemand: Volajícího odepřít nemá žádný vliv na LinkDemand s uplatňovaná oprávnění.**  
**LinkDemand: Volajícího odepřít nemá žádný vliv LinkDemand chráněný kódem.**  
**LinkDemand: Tato odepřít nemá žádný vliv LinkDemand chráněný kódem.**   
## <a name="see-also"></a>Viz také  
 <xref:System.Security.CodeAccessPermission.PermitOnly%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName>   
 <xref:System.Security.CodeAccessPermission.Deny%2A?displayProperty=fullName>   
 <xref:System.Security.IStackWalk.PermitOnly%2A?displayProperty=fullName>   
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   

