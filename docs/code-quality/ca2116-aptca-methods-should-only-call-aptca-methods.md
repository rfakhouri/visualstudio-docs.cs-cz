---
title: "CA2116: Metody APTCA by měly volat pouze metody APTCA | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
helpviewer_keywords:
- AptcaMethodsShouldOnlyCallAptcaMethods
- CA2116
ms.assetid: 8b91637e-891f-4dde-857b-bf8012270ec4
caps.latest.revision: "18"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 92c6a91cffc3ce388a3dfb9000b9f432672018f4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="ca2116-aptca-methods-should-only-call-aptca-methods"></a>CA2116: Metody APTCA by měly volat pouze metody APTCA
|||  
|-|-|  
|TypeName|AptcaMethodsShouldOnlyCallAptcaMethods|  
|CheckId|CA2116|  
|Kategorie|Microsoft.Security|  
|Narušující změna|Narušující|  
  
## <a name="cause"></a>příčina  
 Metoda v sestavení s <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> atribut volá metodu v sestavení, které nemá atribut.  
  
## <a name="rule-description"></a>Popis pravidla  
 Ve výchozím nastavení, jsou veřejných nebo chráněné metody v sestavení se silnými názvy implicitně chráněny [požadavky propojení](/dotnet/framework/misc/link-demands) pro úplný vztah důvěryhodnosti; pouze plně důvěryhodné volající přístup sestavení se silným názvem. Sestavení se silným názvem označené jako <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atribut (APTCA) nemají tato ochrana. Atribut zakáže požadavek propojení zpřístupnění sestavení pro volající, které nemají úplný vztah důvěryhodnosti, například kód provádění z intranetu nebo Internetu.  
  
 Když je atribut APTCA na plně důvěryhodný pro sestavení a sestavení spustí kód v jiném sestavení, který neumožňuje částečně důvěryhodné volající, je možné zneužití zabezpečení. Pokud dvě metody `M1` a `M2` splňovat následující podmínky, škodlivými úmysly můžete použít metodu `M1` obejít požadavek propojení implicitní úplný vztah důvěryhodnosti, který chrání `M2`:  
  
-   `M1`je veřejná metoda deklarována ve plně důvěryhodný pro sestavení, který má atribut APTCA.  
  
-   `M1`volá metodu `M2` mimo `M1`na sestavení.  
  
-   `M2`pro sestavení nemá atribut APTCA a proto by neměl být spouštěn nebo jeho jménem volající, které jsou částečně důvěryhodné.  
  
 Částečně důvěryhodné volající `X` můžete volat metodu `M1`, což způsobilo `M1` volat `M2`. Protože `M2` nemá atribut APTCA jeho bezprostředního volajícího (`M1`) musí splňovat požadavek propojení pro úplný vztah důvěryhodnosti; `M1` má úplný vztah důvěryhodnosti a proto splňuje této kontroly. Je bezpečnostní riziko, protože `X` neúčastní neodpovídajících vyžádání odkaz, který chrání `M2` z nedůvěryhodné volající. Metody s atributem APTCA proto nesmějí volat metody, které nemají atribut.  
  
## <a name="how-to-fix-violations"></a>Jak vyřešit porušení  
 Pokud atribut APTCA je zapotřebí, použijte k ochraně metodu, která volá do úplný vztah důvěryhodnosti sestavení vyžádání. Přesný oprávnění závisí na vyžádání je funkce vystavené metodu. Pokud je možné, chrání metodu o úplný vztah důvěryhodnosti k zajištění, že základní funkce není vystavený částečně důvěryhodné volající. Pokud to není možné, vyberte sadu oprávnění, která efektivně chrání zveřejněné funkce. Další informace o požadavky najdete v tématu [požadavky](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48).  
  
## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění  
 Chcete-li bezpečně potlačit upozornění na toto pravidlo, je nutné zajistit, že funkce vystavené metoda přímo nebo nepřímo neumožňuje volajícím přístup k citlivým informacím, provoz nebo prostředky, které můžete použít destruktivní způsobem.  
  
## <a name="example"></a>Příklad  
 Následující příklad používá dvě sestavení a testovací aplikaci pro ilustraci ohrožení zabezpečení zjistil tímto pravidlem. První sestavení nemá atribut APTCA a nesmí být dostupný pro částečně důvěryhodné volající (reprezentována `M2` v předchozí diskuse).  
  
 [!code-csharp[FxCop.Security.NoAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_1.cs)]  
  
## <a name="example"></a>Příklad  
 Druhý sestavení není plně důvěryhodná a umožňuje částečně důvěryhodné volající (reprezentována `M1` v předchozí diskuse).  
  
 [!code-csharp[FxCop.Security.YesAptca#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_2.cs)]  
  
## <a name="example"></a>Příklad  
 Testovací aplikace (reprezentována `X` v předchozí diskuse) je částečně důvěryhodné.  
  
 [!code-csharp[FxCop.Security.TestAptcaMethods#1](../code-quality/codesnippet/CSharp/ca2116-aptca-methods-should-only-call-aptca-methods_3.cs)]  
  
 Tento příklad vytvoří následující výstup.  
  
 **Vyžádání pro úplné důvěryhodnosti: požadavek se nezdařilo.**  
**ClassRequiringFullTrust.DoWork byla volána.**   
## <a name="related-rules"></a>Související pravidla  
 [CA2117: Typy APTCA by měl rozšířit pouze základní typy APTCA](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)  
  
## <a name="see-also"></a>Viz také  
 [Pokyny pro zabezpečené kódování](/dotnet/standard/security/secure-coding-guidelines)   
 [Sestavení rozhraní .NET framework s částečně důvěryhodným kódem](http://msdn.microsoft.com/en-us/a417fcd4-d3ca-4884-a308-3a1a080eac8d)   
 [Používání knihoven z částečně důvěryhodného kódu](/dotnet/framework/misc/using-libraries-from-partially-trusted-code)   
 [Požadavky](http://msdn.microsoft.com/en-us/e5283e28-2366-4519-b27d-ef5c1ddc1f48)   
 [Požadavky na odkaz](/dotnet/framework/misc/link-demands)   
 [Data a modelování](/dotnet/framework/data/index)