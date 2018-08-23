---
title: 'CA2116: Metody APTCA by měly volat pouze metody APTCA | Dokumentace Microsoftu'
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
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 28a06b789fe790e58d9a3f771cd1f0d8a42db267
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673647"
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: Metody APTCA by měly volat pouze metody APTCA
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CA2116: metody APTCA by měly volat pouze metody APTCA](https://docs.microsoft.com/visualstudio/code-quality/ca2116-aptca-methods-should-only-call-aptca-methods).  
  
TypeName | AptcaMethodsShouldOnlyCallAptcaMethods |  
| ID kontroly | CA2116 |  
| Kategorie | Microsoft.Security|  
| Zásadní změna | Zásadní |  
  
## <a name="cause"></a>příčina  
 Metodu v sestavení <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atribut volá metodu v sestavení, který nemá atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Ve výchozím nastavení, veřejné nebo chráněné metody v podepisují sestavení silnými názvy jsou implicitně chráněné [požadavky propojení](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d) pro úplný vztah důvěryhodnosti; pouze plně důvěryhodní volající může přistupovat k sestavení se silným názvem. Sestavení se silným názvem označené <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atribut (APTCA) nemají tuto ochranu. Atribut zakáže požadavku propojení, zpřístupnění sestavení volajícím, které nemají úplný vztah důvěryhodnosti, jako je například kód provádění z intranetu nebo Internetu.  
  
 Když je atribut APTCA uveden pro plně důvěryhodná sestavení a sestavení spustí kód v jiném sestavení, který neumožňuje volání částečně důvěryhodným volajícím, je možné zneužití zabezpečení. Pokud dvě metody `M1` a `M2` splňovat následující podmínky, škodlivý volající použít metodu `M1` obejít požadavek propojení implicitní úplný vztah důvěryhodnosti, který chrání `M2`:  
  
-   `M1` je v plně důvěryhodná sestavení, který má atribut APTCA deklarována veřejnou metodu.  
  
-   `M1` volá metodu `M2` mimo `M1`pro sestavení.  
  
-   `M2`od sestavení nemá atribut APTCA a proto by neměl být spouštěn podle nebo jejich jménem volajícím, které jsou částečně důvěryhodné.  
  
 Částečně důvěryhodné volající `X` lze zavolat metodu `M1`, způsobující `M1` volat `M2`. Protože `M2` nemá atribut APTCA, jeho bezprostředního volajícího (`M1`) musí uspokojit požadavky propojení pro úplnou důvěryhodnost; `M1` má úplný vztah důvěryhodnosti a proto splňuje tato kontrola. Je bezpečnostní riziko, protože `X` není součástí uspokojit poptávku odkaz, který chrání `M2` z nedůvěryhodných volajících. Metody s atributem APTCA proto nesmějí volat metody, které nemají atribut.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud je vyžadován atribut APTCA, použijte k ochraně metodu, která volá do sestavení úplné důvěryhodnosti vyžádání. Vyžádání vás bude záviset na konkrétní oprávnění funkce vystavené metodu. Pokud je to možné, Chraňte metody s požadavky pro úplný vztah důvěryhodnosti k zajištění toho, že základní funkce není vystaven částečně důvěryhodné volající. Pokud to není možné, vyberte sadu oprávnění, která efektivně chrání vystavené funkce. Další informace o požadavky najdete v tématu [požadavky](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Můžete bezpečně potlačit upozornění tohoto pravidla, ujistěte se, že funkce vystavené metodu přímo nebo nepřímo nepovoluje volající pro přístup k citlivé informace, operace nebo prostředky použité destruktivním způsobem.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá dva sestavení a testovací aplikaci pro ilustraci ohrožení zabezpečení, zjistí toto pravidlo. První sestavení nemá atribut APTCA a by neměl být přístupný pro částečně důvěryhodných volajících (představované `M2` v předchozím diskusí).  
  
 [!code-csharp[FxCop.Security.NoAptca#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.NoAptca/cs/FxCop.Security.NoAptca.cs#1)]  
  
## <a name="example"></a>Příklad  
 Druhý sestavení je plně důvěryhodný a povoluje částečně důvěryhodné volající (představované `M1` v předchozím diskusí).  
  
 [!code-csharp[FxCop.Security.YesAptca#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.YesAptca/cs/FxCop.Security.YesAptca.cs#1)]  
  
## <a name="example"></a>Příklad  
 Testovací aplikace (představované `X` v předchozím diskusí) je částečně důvěryhodné.  
  
 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestAptcaMethods/cs/FxCop.Security.TestAptcaMethods.cs#1)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Požadovat pro úplný vztah důvěryhodnosti: požadavek se nezdařil.**  
**ClassRequiringFullTrust.DoWork byla volána.**   
## <a name="related-rules"></a>Související pravidla  
 [CA2117: Typy APTCA by měly rozšířit pouze základní typy APTCA](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)   
 [Sestavení rozhraní .NET framework volatelná částečně důvěryhodným kódem](http://msdn.microsoft.com/en-us/a417fcd4-d3ca-4884-a308-3a1a080eac8d)   
 [Používání knihoven z částečně důvěryhodného kódu](http://msdn.microsoft.com/library/dd66cd4c-b087-415f-9c3e-94e3a1835f74)   
 [Požadavky](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48)   
 [Požadavky propojení](http://msdn.microsoft.com/library/a33fd5f9-2de9-4653-a4f0-d9df25082c4d)   
 [Data a modelování](http://msdn.microsoft.com/library/8c37635d-e2c1-4b64-a258-61d9e87405e6)



