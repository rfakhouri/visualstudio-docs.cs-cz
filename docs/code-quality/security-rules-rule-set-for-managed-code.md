---
title: Sada pravidel Pravidla zabezpečení pro spravovaný kód
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 564aeac6-03fa-41b0-b655-88179f0ab01b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: c43e1edc2e2aae13fef6df4b4fe414b933067798
ms.sourcegitcommit: b6177ce198c7c5a00030604c9d4faa735405d5df
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/04/2019
ms.locfileid: "59018386"
---
# <a name="security-rules-rule-set-for-managed-code"></a>Sada pravidel Pravidla zabezpečení pro spravovaný kód
Měli byste zahrnout sadu pro maximalizaci počtu možných problémů se zabezpečením, které jsou hlášeny pravidel pravidla zabezpečení společnosti Microsoft.

|Pravidlo|Popis|
|----------|-----------------|
|[CA2100](../code-quality/ca2100-review-sql-queries-for-security-vulnerabilities.md)|Zkontrolujte chyby zabezpečení u dotazů SQL|
|[CA2102](../code-quality/ca2102-catch-non-clscompliant-exceptions-in-general-handlers.md)|Zachycujte výjimky bez CLSCompliant v obecných obslužných rutinách|
|[CA2103](../code-quality/ca2103-review-imperative-security.md)|Zkontrolujte imperativní zabezpečení|
|[CA2104](../code-quality/ca2104-do-not-declare-read-only-mutable-reference-types.md)|Nedeklaruje proměnlivé odkazové typy pouze pro čtení|
|[CA2105](../code-quality/ca2105-array-fields-should-not-be-read-only.md)|Pole s poli by neměla být pouze pro čtení|
|[CA2106](../code-quality/ca2106-secure-asserts.md)|Zabezpečte kontrolní příkazy|
|[CA2107](../code-quality/ca2107-review-deny-and-permit-only-usage.md)|Zkontrolujte použití čistého odepření a povolení|
|[CA2108](../code-quality/ca2108-review-declarative-security-on-value-types.md)|Zkontrolujte deklarativní zabezpečení u typů hodnot|
|[CA2109](../code-quality/ca2109-review-visible-event-handlers.md)|Zkontrolujte viditelné obslužné rutiny událostí|
|[CA2111](../code-quality/ca2111-pointers-should-not-be-visible.md)|Ukazatele by neměly být viditelné|
|[CA2112](../code-quality/ca2112-secured-types-should-not-expose-fields.md)|Zabezpečené typy by neměly vystavovat pole|
|[CA2114](../code-quality/ca2114-method-security-should-be-a-superset-of-type.md)|Zabezpečení metod by mělo být nadmnožinou typu|
|[CA2115](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)|Volejte GC.KeepAlive při použití nativních prostředků|
|[CA2116](../code-quality/ca2116-aptca-methods-should-only-call-aptca-methods.md)|Metody APTCA by měly volat pouze metody APTCA|
|[CA2117](../code-quality/ca2117-aptca-types-should-only-extend-aptca-base-types.md)|Typy APTCA by měl rozšiřovat pouze základní typy APTCA|
|[CA2118](../code-quality/ca2118-review-suppressunmanagedcodesecurityattribute-usage.md)|Zkontrolujte použití SuppressUnmanagedCodeSecurityAttribute|
|[CA2119](../code-quality/ca2119-seal-methods-that-satisfy-private-interfaces.md)|Zapečeťte metody, které vyhovují privátním rozhraním|
|[CA2120](../code-quality/ca2120-secure-serialization-constructors.md)|Zabezpečte serializační konstruktory|
|[CA2121](../code-quality/ca2121-static-constructors-should-be-private.md)|Statické konstruktory by měly být privátní|
|[CA2122](../code-quality/ca2122-do-not-indirectly-expose-methods-with-link-demands.md)|Nezveřejňujte nepřímo metody s požadavky propojení|
|[CA2123](../code-quality/ca2123-override-link-demands-should-be-identical-to-base.md)|Požadavky na propojení přepisů by měly být identické s bází|
|[CA2124](../code-quality/ca2124-wrap-vulnerable-finally-clauses-in-outer-try.md)|Zabalte ohroženou klauzuli finally do vnějšího bloku try|
|[CA2126](../code-quality/ca2126-type-link-demands-require-inheritance-demands.md)|Požadavky na propojení typů vyžadují požadavky na dědičnost|
|[CA2130](../code-quality/ca2130-security-critical-constants-should-be-transparent.md)|Konstanty kritické pro zabezpečení musí být transparentní|
|[CA2131](../code-quality/ca2131-security-critical-types-may-not-participate-in-type-equivalence.md)|Typy kritické pro zabezpečení se nesmí účastnit ekvivalence typů|
|[CA2132](../code-quality/ca2132-default-constructors-must-be-at-least-as-critical-as-base-type-default-constructors.md)|Výchozí konstruktory musí být alespoň tak kritické, jako výchozí konstruktory základního typu|
|[CA2133](../code-quality/ca2133-delegates-must-bind-to-methods-with-consistent-transparency.md)|Delegáti musí mít vazbu s metodami s konzistentní transparentností|
|[CA2134](../code-quality/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods.md)|Metody musí při přepisování základních metod zachovávat konzistentní transparentnost|
|[CA2135](../code-quality/ca2135-level-2-assemblies-should-not-contain-linkdemands.md)|Sestavení úrovně 2 by neměla obsahovat LinkDemands|
|[CA2136](../code-quality/ca2136-members-should-not-have-conflicting-transparency-annotations.md)|Členy by neměly mít konfliktní poznámky transparentnosti|
|[CA2137](../code-quality/ca2137-transparent-methods-must-contain-only-verifiable-il.md)|Transparentní metody musí obsahovat pouze ověřitelné IL|
|[CA2138](../code-quality/ca2138-transparent-methods-must-not-call-methods-with-the-suppressunmanagedcodesecurity-attribute.md)|Transparentní metody nesmí volat metody s atributem SuppressUnmanagedCodeSecurity|
|[CA2139](../code-quality/ca2139-transparent-methods-may-not-use-the-handleprocesscorruptingexceptions-attribute.md)|Transparentní metody nemusí používat atribut HandleProcessCorruptingExceptions|
|[CA2140](../code-quality/ca2140-transparent-code-must-not-reference-security-critical-items.md)|Transparentní kód nesmí odkazovat na položky kritické pro zabezpečení|
|[CA2141](../code-quality/ca2141-transparent-methods-must-not-satisfy-linkdemands.md)|Transparentní metody nesmějí vyhovovat LinkDemands|
|[CA2142](../code-quality/ca2142-transparent-code-should-not-be-protected-with-linkdemands.md)|Transparentní kód by neměl být chráněn pomocí LinkDemands|
|[CA2143](../code-quality/ca2143-transparent-methods-should-not-use-security-demands.md)|Transparentní metody by neměly používat požadavky zabezpečení|
|[CA2144](../code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays.md)|Transparentní kód by neměl načítat sestavení z bajtových polí|
|[CA2145](../code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute.md)|Transparentní metody by neměly být doplněny o SuppressUnmanagedCodeSecurityAttribute|
|[CA2146](../code-quality/ca2146-types-must-be-at-least-as-critical-as-their-base-types-and-interfaces.md)|Typy musí být alespoň tak kritické, jako jejich základní typy a rozhraní|
|[CA2147](../code-quality/ca2147-transparent-methods-may-not-use-security-asserts.md)|Transparentní metody nemusí používat kontrolní příkazy zabezpečení|
|[CA2149](../code-quality/ca2149-transparent-methods-must-not-call-into-native-code.md)|Transparentní metody nesmí provádět volání nativního kódu|
|[CA2210](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|Sestavení by měla mít platné silné názvy|
|[CA3001](../code-quality/ca3001-review-code-for-sql-injection-vulnerabilities.md)|Prohlédněte si kód pro chyby prostřednictvím injektáže SQL|
|[CA3002](../code-quality/ca3002-review-code-for-xss-vulnerabilities.md)|Revize kódu XSS ohrožení zabezpečení|
|[CA3003](../code-quality/ca3003-review-code-for-file-path-injection-vulnerabilities.md)|Prohlédněte si kód pro chyby vkládání cesta souboru|
|[CA3004](../code-quality/ca3004-review-code-for-information-disclosure-vulnerabilities.md)|Prohlédněte si kód pro zveřejnění informace o ohrožení zabezpečení|
|[CA3005](../code-quality/ca3005-review-code-for-ldap-injection-vulnerabilities.md)|Prohlédněte si kód pro vkládání LDAP ohrožení zabezpečení|
|[CA3006](../code-quality/ca3006-review-code-for-process-command-injection-vulnerabilities.md)|Prohlédněte si kód pro proces příkaz vkládání ohrožení zabezpečení|
|[CA3007](../code-quality/ca3007-review-code-for-open-redirect-vulnerabilities.md)|Prohlédněte si kód pro chyby na otevřeném přesměrování|
|[CA3008](../code-quality/ca3008-review-code-for-xpath-injection-vulnerabilities.md)|Revize kódu pro výraz XPath vkládání chyb zabezpečení|
|[CA3009](../code-quality/ca3009-review-code-for-xml-injection-vulnerabilities.md)|Revize kódu XML vkládání chyb zabezpečení|
|[CA3010](../code-quality/ca3010-review-code-for-xaml-injection-vulnerabilities.md)|Revize kódu XAML vkládání chyb zabezpečení|
|[CA3011](../code-quality/ca3011-review-code-for-dll-injection-vulnerabilities.md)|Revize kódu pro knihovnu DLL vkládání ohrožení zabezpečení|
|[CA3012](../code-quality/ca3012-review-code-for-regex-injection-vulnerabilities.md)|Prohlédněte si kód pro vkládání regulární výraz ohrožení zabezpečení|
