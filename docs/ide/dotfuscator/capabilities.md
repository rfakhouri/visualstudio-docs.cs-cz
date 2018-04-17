---
title: Možnosti Dotfuscatoru | Microsoft Docs
ms.date: 2017-10-10
ms.devlang: dotnet
ms.technology:
- vs-ide-general
ms.topic: conceptual
keywords: Dotfuscatoru, Dotfuscatoru CE, preemptivní, preemptivní řešení preemptivní ochrana, ochrana, edice community, maskováním, .NET, volná, Visual Studio 2017
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: Další možnosti Bezplatná edice Community Dotfuscatoru součástí Visual Studio 2017.
ms.assetid: 0ee89c58-c900-48fc-a6a2-65ace00e8bab
author: Joe-Sewell-PreEmptive
manager: douge
ms.openlocfilehash: 91d2e379c37567a88e29eb504ad7bc09723d3fc6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="capabilities-of-dotfuscator"></a>Možnosti Dotfuscatoru

Tato stránka se zaměřuje na možnostech Dotfuscatoru Community Edition (Dotfuscatoru CE) s některé odkazy na rozšířené možnosti, které jsou k dispozici prostřednictvím [upgrady][upgrades].

Je Dotfuscatoru *po sestavení* systému pro aplikace .NET.
S Dotfuscatoru CE, budou moct uživatelé sady Visual Studio [obfuskováním sestavení] [ obfuscation] a vložit [active obrany] [ checks] a [analytics sledování] [ analytics] do aplikace – všechny bez Dotfuscatoru, která potřebuje přístup k původní zdrojový kód.
Dotfuscatoru chrání aplikace několika způsoby vytváření strategie vrstveného ochrany.

Dotfuscatoru CE podporuje široký rozsah .NET sestavení a aplikace typů, včetně [univerzální platformu Windows (UWP)] [ uwp] a [Xamarin] [ xamarin].

## <a name="intellectual-property-protection"></a>Ochrany duševního vlastnictví

Návrh vaší aplikace, chování a implementace jsou formy duševního vlastnictví (IP).
Aplikace vytvořené pro rozhraní .NET Framework jsou však v podstatě otevřete knih; je velmi snadné sestavení .NET zpětné analýzy, [jako obsahují podrobný metadata a zprostředkující kódu][assemblies].

Obsahuje základní Dotfuscatoru CE [.NET maskováním] [ obfuscation] ve formě [přejmenování][renaming].
Zmatení data kódu s Dotfuscatoru snižuje riziko neoprávněného přístupu ke zdrojovému kódu prostřednictvím zpětnou analýzu, jako důležité informace o názvech už být veřejné.
Maskováním také ukazuje úsilí na vaše role při ochraně kódu z prozkoumání - cenné krok v zřízení, že je vaše IP právními předpisy chráněna jako obchodní tajemství.

Řadu [funkce ochrany integrity aplikace](#application-integrity-protection) z Dotfuscatoru CE další brání reverse inženýrství.
Pro instanci objektu actor chybný pokusit připojit ladicí program ke spuštěné instanci vaší aplikace. Chcete-li pochopit logiku programu.
Můžete vložit Dotfuscatoru [chování proti ladění] [ debug] do aplikace, abyste to bránilo.

## <a name="application-integrity-protection"></a>Ochrana Integrity aplikace

Kromě ochrany vašeho zdrojového kódu, je také důležité zajistit, že se vaše aplikace používá navrženou.
Útočníci se můžou snažit napadnout vaší aplikaci, aby obešel licencování zásady (tj. softwarové pirátství) ukrást nebo manipulaci s citlivá data, provádí aplikace, nebo můžete změnit chování aplikace.

Můžete vložit Dotfuscatoru CE [ověření kódu aplikace] [ checks] do vaší sestavení, včetně [proti zfalšování] [ tamper] a [proti ladění] [ debug] míry.
Pokud je zjištěn stav neplatný aplikace, kód ověřování můžete [zvát kód aplikace na adresu situaci vhodným způsobem][check-app].
Nebo, pokud nechcete napsat kód pro neplatný popisovač používá aplikace, můžete také vložit Dotfuscatoru [telemetrie reporting] [ check-telemetry] a [odpovědi] [ check-action] chování, aniž by jakékoli změny vašeho zdrojového kódu.

Mnoho z těchto metod stejné může být použit k vytvoření [ukončenou životností termíny] [ shelflife] pro zkušební verzi nebo zkušební verze softwaru.

## <a name="application-monitoring"></a>Monitorování aplikací

Při vývoji aplikace, je zásadně důležité pochopit vzorce chování uživatelů, včetně beta testery a uživatelé předchozí verze.
Analýza aplikace umožňuje sledovat, jak často se používá aplikace a jak se používají včetně jaké chyby zákazníků zaznamenat.

Můžete vložit Dotfuscatoru CE [sledování výjimek][exceptions], [sledování relace][sessions], a [funkce sledování] [ features] kódu do své aplikace.
Při spuštění, zpracovaná aplikace budou odesílat data analýzy nakonfigurované [preemptivní Analytics endpoint][endpoints].

## <a name="see-also"></a>Viz také

[Toto téma v úplné Dotfuscatoru CE uživatelská příručka][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[assemblies]: https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
[uwp]: https://www.preemptive.com/blog/article/856-uwp-applications-in-dotfuscator-ce/91-dotfuscator-ce
[xamarin]: https://www.preemptive.com/obfuscating-xamarin-with-dotfuscator

[upgrades]: upgrades.md

[obfuscation]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_overview.html
[renaming]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[analytics]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_overview.html
[endpoints]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_overview.html#endpoints

[checks]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[check-app]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#app-notification
[check-action]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#action

[tamper]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[shelflife]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html
[exceptions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_exceptions.html
[sessions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_sessions.html
[features]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_features.html
[check-telemetry]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_checks.html

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_capabilities.html
