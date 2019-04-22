---
title: Upgrade Dotfuscatoru Community
ms.date: 03/28/2019
ms.devlang: dotnet
ms.topic: conceptual
keywords: Nástroj Dotfuscator, nástroj Dotfuscator Community, řešení Dotfuscator CE, PreEmptive, společnosti PreEmptive Solutions PreEmptive ochrany, ochranu, community edition, obfuskace, .NET, bezplatný, Visual Studio. 2019, Visual Studio 2017, Visual Studio, upgrade, příkazový řádek
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator Community
- Dotfuscator
- obfuscation
- protection
- Dotfuscator upgrade
- upgrade Dotfuscator
- upgrading Dotfuscator
- register Dotfuscator
- registering Dotfuscator
- Dotfuscator command line
- Dotfuscator Professional
description: Zjistěte, jak upgradovat bezplatnou kopii verze nástroje Dotfuscator Community součástí sady Visual Studio.
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: cee876a3904d5c47b43b58793087c901e8444dd3
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2019
ms.locfileid: "58866676"
---
# <a name="upgrade-dotfuscator-community"></a>Upgrade Dotfuscatoru Community

Nástroj Dotfuscator Community nabízí mnoho Ochrana aplikace a funkce pro posílení zabezpečení okamžitě pro všechny vývojáře, kteří používají Microsoft Visual Studio.
Existují však další funkce dostupné pro uživatele, kteří upgrade řešení dotfuscator jejich verze.

## <a name="registering-dotfuscator-community"></a>Registrace Nástroje Dotfuscator Community

Registrovaných uživatelů nástroj Dotfuscator Community získat přístup k dalším funkcím, jako například [podpory příkazového řádku][cli], což usnadňuje integraci řešení Dotfuscator Community do procesu automatické sestavení . Registrace poskytuje také přístup k vestavěné nástroj používaný pro [dekódování trasování zásobníku obfuskovaný][decode-obfuscated].

Registrace je rychlé, jednoduché a zadarmo.
Zaregistrovat nástroj Dotfuscator Community, najdete v článku [podle pokynů v uživatelské příručce nástroje úplné řešení Dotfuscator Community][register-ce].

## <a name="dotfuscator-professional"></a>Nástroje Dotfuscator Professional

Během Dotfuscator Community poskytuje základní úroveň ochrany, ***PreEmptive ochrany - nástroje Dotfuscator Professional*** zahrnuje vylepšené obfuskace transformace a možnosti ochrany, například:

* *Ochranu duševního vlastnictví*
  * Další možnosti, včetně Enhanced Overload Induction™ a výběru náhodného identifikátor přejmenování.
  * Přístup k podnikové úrovni obfuskace transformací, včetně [transformace zaměřený na vytvoříte automatizované kód dekompilace][control-flow].
  * Schopnost [skryl citlivé řetězce][string-encryption], provádění možné jednoduché hledání dekompilované kódu.
  * Schopnost [diskrétní vlastnictví a distribuci řetězce vložení do sestavení][watermarking], umožňuje určit příčiny Neautorizováno nevracení softwaru.
  * Schopnost [kombinovat více sestavení do jednoho][linking], znesnadňuje i pro útočníky k určení rolí prvků kódu, protože byly odstraněny oddělení oblastí zájmu.
  * Schopnost [automaticky odebrat nepoužitý kód ze své aplikace][pruning], čímž snižuje velikost citlivé kód, který je dodáván.
* *Ochrana Integrity aplikace*
  * Další [chování aplikací defense][check-actions].
  * Schopnost poskytnout určité upozornění před konečným termínem ukončenou životností aplikace.
  * Možnost oznámit kód aplikace během období upozornění ukončenou životností nebo po konečném termínu.

Nástroje Dotfuscator Professional je standardní průmyslový [.NET Obfuskátor] [ net-obfuscator] a je vhodný pro podnikové vývojáře vyžadující probíhajících aktualizacích fungovat podporu, údržby a produktu.
Kromě toho nástroje Dotfuscator Professional nabízí užší integraci s Visual Studio a má licenci pro obchodní použití.

Další informace o funkcích pokročilé aplikace ochrany nástroje Dotfuscator Professional, najdete na webu společnosti PreEmptive Solutions [stránka s přehledem nástroje Dotfuscator] [ product-about] a [porovnat s Nástroj Dotfuscator Community][product-compare].
[Plně podporované zkušební verze najdete na adrese preemptive.com][eval].

## <a name="see-also"></a>Viz také

[Tento článek v uživatelské příručce nástroje úplné řešení Dotfuscator Community][full]

<!-- Copyright © 2019 PreEmptive Solutions, LLC -->

[control-flow]:  https://www.preemptive.com/products/dotfuscator/features#controlflow
[string-encryption]:  https://www.preemptive.com/products/dotfuscator/features#string
[watermarking]:  https://www.preemptive.com/products/dotfuscator/features#watermarking
[linking]:  https://www.preemptive.com/products/dotfuscator/features#linking
[pruning]:  https://www.preemptive.com/products/dotfuscator/features#pruning

[check-actions]:  https://www.preemptive.com/dotfuscator/pro/userguide/en/protection_checks_overview.html#actions

[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[eval]:  https://www.preemptive.com/eval-request

[product-about]:  https://www.preemptive.com/products/dotfuscator/overview
[product-compare]:  https://www.preemptive.com/products/dotfuscator/compare-editions

[cli]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
[register-ce]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html
[decode-obfuscated]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_decode_stack_trace.html