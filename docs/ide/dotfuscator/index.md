---
title: Dotfuscatoru Community Edition (CE)
ms.date: 10/10/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscatoru, Dotfuscatoru CE, preemptivní, preemptivní řešení preemptivní ochrana, ochrana, edice community, maskováním, .NET, volná, Visual Studio 2017
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: Zjistěte, jak lze chránit aplikací .NET bezplatná edice Community Dotfuscatoru součástí Visual Studio 2017.
ms.assetid: d9550502-0a82-49a6-b005-2caa791fbe02
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: a81d640e2ecebe46a20f7a3661584cb5c7423691
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/04/2018
---
# <a name="dotfuscator-community-edition-ce"></a>Dotfuscatoru Community Edition (CE)

*Preemptivní ochrana – Dotfuscatoru* poskytuje komplexní ochranu aplikace .NET to snadné pro rozlišení do vaší zabezpečené softwaru životního cyklu.
Použijte ho k posílení zabezpečení, ochraně a vyřadit plochy, mobilní, server a vložená aplikací do zabezpečené obchodního tajemství a jiné duševní vlastnictví (IP), snížit pirátství a padělání a chránit proti manipulaci a neoprávněným ladění.
Dotfuscatoru funguje na kompilované sestavení bez nutnosti dalšího programování nebo i přístup ke zdrojovému kódu.

![Preemptivní ochrana – Dotfuscatoru](media/header.svg)

## <a name="why-protection-matters"></a>Proč na záleží ochrany

Je důležité **chránit duševní vlastnictví** (IP).
Kód aplikace obsahuje informace návrhu a implementace, které lze považovat za IP.
Ale aplikací postavené na rozhraní .NET Framework [zahrnují významné metadata a nejdůležitější zprostředkující kód][assemblies], přitom snadno provádět zpětnou analýzu, právě pomocí jedné z mnoha volná, automatizované nástroje.
Přerušení a zastavení zpětnou vám může zabránit neoprávněným sdílením IP, stejně jako ukazují, že kód obsahuje obchodních tajemství.
Můžete Dotfuscatoru [obfuskováním] [ obfuscation] vaše sestavení .NET bránit zpětnou, při zachování původní chování aplikace.

Je také důležité **chránit integritu aplikace**.
Kromě zpětnou nesprávnými účastníky můžou snažit pirate vaší aplikace, změnit chování aplikace za běhu nebo pracovat s daty.
Dotfuscatoru může vložit vaše aplikace se schopností [zjišťovat, sestavy a reagovat na neoprávněným použitím][checks], včetně manipulaci s obsahem a ladění třetích stran.

Další informace o jak Dotfuscatoru zapadá do životního cyklu zabezpečené softwaru najdete v tématu preemptivní řešení [SDL aplikaci ochrany stránky][sdl-protection].

## <a name="about-dotfuscator-ce"></a>O Dotfuscatoru CE

Vaší kopie aplikace Microsoft Visual Studio 2017 obsahuje kopii  ***preemptivní ochrana – Dotfuscatoru* Community Edition**, označované také jako Dotfuscatoru CE zdarma pro osobní použití.
Pokyny o tom, jak nainstalovat verzi Dotfuscatoru CE součástí Visual Studio 2017 najdete v tématu [instalační stránka][install].

Dotfuscatoru CE nabízí řadu [ochrany před softwarem a posílení zabezpečení] [ software-protection] služby pro vývojáře, architekty a testerům, sada.
Příklady [.NET maskováním] [ obfuscation] a dalších [Ochrana aplikace] [ app-protection] jsou funkce obsažené v Dotfuscatoru CE:

* *[Přejmenování] [ renaming]*  identifikátorů ztížit zpětnou kompilované sestavení.
* *[Proti zfalšování] [ tamper]*  k detekci spuštění zmanipulovanou aplikací, přenášet incidentu výstrahy a ukončete zmanipulovanou relací.
* *[Proti ladění] [ debug]*  ke zjištění připojení ladicí program k spuštěné aplikace, přenášet incidentu výstrahy a ukončete vyladěnou relací.
* *[Chování vypršení platnosti aplikací] [ shelflife]*  , kódovat datum "end životnosti", přenášet výstrahy, když se aplikace spustí po vypršení jejich platnosti a ukončení relace vypršela platnost aplikace.
* *[Sledování výjimek] [ exceptions]*  ke sledování neošetřených výjimek, které se vyskytují v rámci aplikace.
* *[Relace] [ sessions] a [funkce] [ features] sledování využití* Chcete-li zjistit, co aplikace byly spustit, jaké verze těchto aplikací a jaké funkce se používají v těchto aplikacích.

Podrobné informace týkající se těchto funkcí, včetně toho, jak je začlenit do strategie ochrany aplikací najdete [možnosti stránky][capabilities].

Dotfuscatoru CE nabízí základní ochrany out-of-the-box.
I další ochranná opatření aplikace jsou dostupné na registrovaní uživatelé Dotfuscatoru CE a uživatelům *preemptivní ochrana – Dotfuscatoru* Professional Edition, je na světě úvodní [.NET Obfuscator] [net-obfuscator].
Informace o rozšíření Dotfuscatoru najdete v tématu [upgrady stránky][upgrades].

## <a name="getting-started"></a>Začínáme

Chcete-li začít používat Dotfuscatoru CE ze sady Visual Studio, zadejte `dotfuscator` do **Snadné spuštění** panelu Hledat (Ctrl + Q).

* Pokud Dotfuscatoru CE je již nainstalován, **Snadné spuštění** otevře *nabídky* možnost spustit uživatelské rozhraní Dotfuscatoru CE. Podrobnosti najdete v tématu [stránce Začínáme v úplné uživatelské příručce CE Dotfuscatoru][get-started].
* Pokud ještě není nainstalovaná Dotfuscatoru CE, **Snadné spuštění** vyvoláte odpovídajícího *nainstalovat* možnost. Najdete v článku [instalační stránka] [ install] podrobnosti.

Můžete získat také **nejnovější verzi** z Dotfuscatoru CE z [Dotfuscatoru stáhne stránky na preemptive.com][download].

## <a name="full-documentation"></a>Úplnou dokumentaci

Tato stránka a její podstránky poskytují přehled funkcí Dotfuscatoru CE, a také [pokyny k instalaci nástroje][install].

V tématu [v úplné Dotfuscatoru CE uživatelské příručce na preemptive.com] [ full] podrobné pokyny k použití, včetně [spuštění pomocí uživatelského rozhraní Dotfuscatoru CE] [ get-started].

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

- [assemblies]: https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
- [software-protection]: https://www.preemptive.com/software-protection
- [obfuscation]: https://www.preemptive.com/obfuscation
- [app-protection]: https://www.preemptive.com/application-protection
- [sdl-protection]: https://www.preemptive.com/solutions/SDL-App-Protection
- [net-obfuscator]: https://www.preemptive.com/products/dotfuscator/overview
- [download]: https://www.preemptive.com/products/dotfuscator/downloads

- [install]: install.md
- [capabilities]: capabilities.md
- [upgrades]: upgrades.md

- [get-started]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

- [renaming]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

- [checks]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
- [tamper]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
- [debug]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
- [shelflife]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html

- [exceptions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_exceptions.html
- [sessions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_sessions.html
- [features]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_features.html

- [full]: https://www.preemptive.com/dotfuscator/ce/docs/help/index.html