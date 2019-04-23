---
title: Dotfuscator Community
ms.date: 03/28/2019
ms.devlang: dotnet
ms.topic: conceptual
keywords: Nástroj Dotfuscator, řešení Dotfuscator CE, nástroj Dotfuscator Community, PreEmptive, společnosti PreEmptive Solutions PreEmptive ochrany, ochranu, community edition, obfuskace, .NET, bezplatný, Visual Studio. 2019, Visual Studio 2017, Visual Studio
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator Community
- Dotfuscator
- obfuscation
- protection
description: Zjistěte, jak můžete ochránit vaše aplikace .NET s bezplatnou kopii nástroje Dotfuscator Community součástí sady Visual Studio.
ms.assetid: d9550502-0a82-49a6-b005-2caa791fbe02
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bf77f2796a224d6fad81c4a1485ba82f8822cfcc
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60058366"
---
# <a name="dotfuscator-community"></a>Dotfuscator Community

***PreEmptive ochranu – řešení Dotfuscator*** poskytuje komplexní ochranu aplikací .NET snadno přizpůsobí do vývojového cyklu zabezpečeného softwaru.
Použijte ho k posílení zabezpečení, ochraně a vyřadit plochy, mobilních, server a vložené aplikace zabezpečené obchodní tajemství a jinému duševnímu (IP), snížit pirátství a padělání a Chraňte se proti manipulaci a neoprávněným ladění.
Nástroj Dotfuscator funguje v kompilovaných sestavení bez potřeby dalšího programování nebo dokonce i přístup ke zdrojovému kódu.

![PreEmptive ochranu – řešení Dotfuscator](media/header.svg)

## <a name="why-protection-matters"></a>Proč na záleží ochrany

Je důležité **chránit duševní vlastnictví** (IP).
Kód vaší aplikace obsahuje návrhu a podrobnosti implementace, které lze považovat za IP.
Ale aplikace založená na rozhraní .NET Framework [významné metadat a základní mezikódu obsahovat][assemblies], provedení je snadné provést zpětnou analýzu, stačí použít jeden z mnoha zdarma, automatizovat nástroje.
Přerušení a zastavení zpětné analýzy vám může zabránit neautorizovaným zveřejněním IP, jakož i prokázat, že váš kód obsahuje tajemství.
Nástroje Dotfuscator můžete [obfuskaci] [ obfuscation] sestavení .NET bránit zpětné analýzy, při zachování původního chování aplikace.

Je také důležité **chrání integritu aplikace**.
Kromě zpětné analýzy můžou snažit nesprávnými účastníky pirate vaší aplikace, měnit chování aplikace za běhu ani manipulaci s daty.
Nástroje Dotfuscator můžete vkládat aplikace možnost [rozpoznání hrozeb a reakce na neoprávněné použití][checks], včetně úmyslné poškozování, ladění třetích stran a zařízením s rootem.

Další informace o jak řešení Dotfuscator zapadá do životního cyklu vývoje zabezpečeného softwaru, najdete v článku společnosti PreEmptive Solutions [SDL App Protection stránky][sdl-protection].

## <a name="about-dotfuscator-community"></a>Informace o řešení Dotfuscator Community

Vaše kopie sady Microsoft Visual Studio obsahuje kopii ***PreEmptive ochranu – nástroj Dotfuscator Community***, zdarma pro osobní použití.
(Tato bezplatná verze byla dříve označovanou jako nástroj Dotfuscator Community Edition nebo řešení Dotfuscator CE.) Pokyny o tom, jak nainstalovat verzi nástroje Dotfuscator Community součástí sady Visual Studio najdete v tématu [stránky instalace][install].

Nástroj Dotfuscator Community nabízí celou řadu [ochrany před softwarem a posílení zabezpečení] [ software-protection] služby pro vývojáře, architekty a testery.
Příklady [.NET obfuskace] [ obfuscation] a dalších [Ochrana aplikace] [ app-protection] jsou funkce obsažené v řešení Dotfuscator Community:

* *[Přejmenování] [ renaming]*  identifikátorů, které mají ztížit zpětnou zkompilovaného sestavení.
* *[Boj proti] [ tamper]*  k detekci spuštění zmanipulovanou aplikací a ukončit nebo v reakci na manipulováno relace.
* *[Ladění proti] [ debug]*  -li zjistit přílohy ladicího programu k běžící aplikaci a ukončit nebo reakce na ladit relace.
* *[Zařízení s rootem proti] [ root]*  -li zjistit, pokud aplikace běží na rootovaném zařízení s Androidem a ukončit nebo reakce na relace na těchto zařízeních.
* *[Chování vypršení platnosti aplikací] [ shelflife]*  , který kódování datem "ukončení životnosti technologie" a ukončí aplikaci vypršela platnost relace.

Podrobnosti o těchto funkcích, včetně toho, jak se vešly do strategie ochrany aplikací najdete v tématu [stránka schopnosti][capabilities].

Nástroj Dotfuscator Community nabízí základní ochranu out-of-the-box.
Ještě více opatření na ochranu aplikací jsou k dispozici pro registrovaného uživatele nástroj Dotfuscator Community a uživatelům ***PreEmptive ochrany - nástroje Dotfuscator Professional***, nejlepší na světě [.NET Obfuskátor] [net-obfuscator].
Informace o rozšíření Dotfuscator, najdete v článku [stránce upgrady][upgrades].

## <a name="getting-started"></a>Začínáme

::: moniker range="vs-2019"

Chcete-li začít používat nástroj Dotfuscator Community ze sady Visual Studio, zadejte `dotfuscator` do **vyhledávacího pole** (Ctrl + Q).

* Pokud nástroj Dotfuscator Community je už nainstalovaný, **vyhledávacího pole** se zobrazí možnost spustit nástroj Dotfuscator Community v části *nabídky* záhlaví. Podrobnosti najdete v tématu [stránku Začínáme úplné řešení Dotfuscator Community uživatelské příručce nástroje][get-started].
* Pokud ještě není nainstalovaný nástroj Dotfuscator Community, **vyhledávacího pole** místo toho zobrazí **instalace nástroje PreEmptive ochranu – řešení Dotfuscator** pod *jednotlivé komponenty* záhlaví . Zobrazit [stránky instalace] [ install] podrobnosti.

::: moniker-end

::: moniker range="vs-2017"

Chcete-li začít používat nástroj Dotfuscator Community ze sady Visual Studio, zadejte `dotfuscator` do **Snadné spuštění** panelu hledání (Ctrl + Q).

* Pokud nástroj Dotfuscator Community je už nainstalovaný, **Snadné spuštění** vyvolá *nabídky* možnosti spuštění uživatelského rozhraní nástroje Dotfuscator Community. Podrobnosti najdete v tématu [stránku Začínáme úplné řešení Dotfuscator Community uživatelské příručce nástroje][get-started].
* Pokud ještě není nainstalovaný nástroj Dotfuscator Community, **Snadné spuštění** zobrazí příslušné *nainstalovat* možnost. Zobrazit [stránky instalace] [ install] podrobnosti.

::: moniker-end

Můžete získat také **nejnovější verzi** nástroje Dotfuscator Community z [stránce soubory ke stažení nástroje Dotfuscator preemptive.com][download].

## <a name="full-documentation"></a>Úplnou dokumentaci

Na této stránce a její podstránky poskytují přehled funkce řešení Dotfuscator Community, stejně jako [pokyny k instalaci nástroje][install].

Zobrazit [úplného Průvodce uživatele řešení Dotfuscator Community v preemptive.com] [ full] podrobné pokyny k použití, včetně [spuštění pomocí uživatelského rozhraní nástroje Dotfuscator Community][get-started].

<!-- Copyright © 2019 PreEmptive Solutions, LLC -->

[assemblies]:  https://docs.microsoft.com/dotnet/standard/assembly-format
[software-protection]:  https://www.preemptive.com/software-protection
[obfuscation]:  https://www.preemptive.com/obfuscation
[app-protection]:  https://www.preemptive.com/application-protection
[sdl-protection]:  https://www.preemptive.com/solutions/SDL-App-Protection
[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[download]:  https://www.preemptive.com/products/dotfuscator/downloads

[install]:  install.md
[capabilities]:  capabilities.md
[upgrades]:  upgrades.md

[get-started]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

[renaming]:  https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[checks]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[tamper]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[root]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_root.html
[shelflife]:  https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/index.html
