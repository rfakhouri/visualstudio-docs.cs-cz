---
title: Upgrade edice Community Dotfuscatoru (CE)
ms.date: 02/08/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscatoru, Dotfuscatoru CE, preemptivní, preemptivní řešení preemptivní ochrana, ochrana, edice community, maskováním, .NET, volná, Visual Studio 2017, upgradu, příkazového řádku
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
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
description: Naučte se upgradovat bezplatná edice Community Dotfuscatoru součástí Visual Studio 2017.
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: fcd5832b52c6cd9f72829c2bce8f7813b682cf4f
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704571"
---
# <a name="upgrade-dotfuscator-community-edition-ce"></a>Upgrade edice Community Dotfuscatoru (CE)

Dotfuscatoru Community Edition (Dotfuscatoru CE) nabízí mnoho Ochrana aplikace a funkce posílení zabezpečení okamžitě pro všechny vývojáře pomocí sady Microsoft Visual Studio.
Však nejsou k dispozici pro uživatele, kteří upgrade jejich verzi Dotfuscatoru další funkce.

## <a name="registering-dotfuscator-ce"></a>Registrace Dotfuscatoru CE

Registrovaní uživatelé Dotfuscatoru CE získat přístup k dalším funkcím, jako například [podporu příkazového řádku][cli], což usnadňuje integraci Dotfuscatoru CE do procesu automatizované sestavení. Registrace také uděluje přístup k Lucidator, integrované nástroj používaný pro [dekódování trasování zásobníku zkomolené][decode-obfuscated].

Registrace je rychlá, jednoduchá a zdarma.
Chcete-li zaregistrovat Dotfuscatoru CE, přečtěte si téma [části registrace CE Dotfuscatoru na stránce Začínáme v úplné uživatelské příručce CE Dotfuscatoru][register-ce].

## <a name="dotfuscator-professional"></a>Dotfuscatoru Professional

Zatímco Dotfuscatoru Community Edition poskytuje základní úroveň ochrany,  **_preemptivní ochrana – Dotfuscatoru_ Professional Edition** zahrnuje rozšířené maskováním transformací a ochrany Možnosti. Rozšířené transformací a možnosti patří:

* *Ochrany duševního vlastnictví*
  * Další možnosti, včetně Enhanced Overload Induction™ a výběr náhodnou identifikátor přejmenování.
  * Nástroje pro dekódování matoucí trasování zásobníku.
  * Přístup k podnikové úrovni maskováním transformací, včetně [transformací zaměřený na narušen automatizované kód dekompilace][control-flow].
  * Schopnost [skrývat citlivé řetězce][string-encryption], což znemožňuje jednoduché hledání decompiled kódu.
  * Schopnost [diskrétní vlastnictví a distribuci řetězce vložení do vaší sestavení][watermarking], díky tomu můžete určit zdroj Neautorizováno nevracení softwaru.
  * Schopnost [kombinovat více sestavení do jednoho][linking], znesnadňuje i pro útočníky určení rolí elementy kódu jako oddělené oblasti zájmu se odstranilo.
  * Schopnost [automaticky odstranit nepoužívané kód z vaší aplikace][pruning], snižuje množství citlivé kód, který je součástí.
* *Ochrana Integrity aplikace*
  * Další [chování aplikací obrany][check-actions].
  * Schopnost poskytovat období upozornění před termínem aplikace ukončenou životností.
  * Možnost oznámení kód aplikace během období upozornění ukončenou životností nebo po dosažení konečného termínu.
  * Telemetrická data šifrování.
* *Monitorování aplikací*
  * Umožňuje shromáždit a uložit shromažďují informace během výpadků dočasné sítě.
  * Schopnost shromažďovat identifikovatelné osobní údaje.
  * Neomezená použití [funkce sledování][features].
  * Možnost sledování výjimek zachycení a vyvolané kódu, navíc k neošetřených výjimek.
  * Ke sledování výjimek v `.dll` sestavení.
  * Telemetrická data šifrování.

Professional Dotfuscatoru je oborový standard [.NET Obfuscator] [ net-obfuscator] a je vhodný pro vývojáře vyžadujících probíhající aktualizaci podpory, údržbu a produktu.
Kromě toho Dotfuscatoru Professional nabízí užší integrace se sadou Visual Studio a má licenci pro komerční použití.

Další informace o funkcí pokročilé aplikací ochrany Dotfuscatoru Professional, navštivte preemptivní řešení [stránku přehled Dotfuscatoru] [ product-about] a [porovnat s Edice Community][product-compare].
[Zkušební plně podporované verze jsou k dispozici na preemptive.com][eval].

## <a name="see-also"></a>Viz také

[Tento článek v úplné Dotfuscatoru CE uživatelská příručka][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[control-flow]:  https://www.preemptive.com/products/dotfuscator/features#controlflow
[string-encryption]:  https://www.preemptive.com/products/dotfuscator/features#string
[watermarking]:  https://www.preemptive.com/products/dotfuscator/features#watermarking
[linking]:  https://www.preemptive.com/products/dotfuscator/features#linking
[pruning]:  https://www.preemptive.com/products/dotfuscator/features#pruning

[check-actions]:  https://www.preemptive.com/dotfuscator/pro/userguide/en/protection_checks_overview.html#actions
[features]:  https://www.preemptive.com/dotfuscator/pro/userguide/en/instrumentation_features.html

[net-obfuscator]:  https://www.preemptive.com/products/dotfuscator/overview
[eval]:  https://www.preemptive.com/eval-request

[product-about]:  https://www.preemptive.com/products/dotfuscator/overview
[product-compare]:  https://www.preemptive.com/products/dotfuscator/compare-editions

[cli]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
[register-ce]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

[full]:  https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html
[decode-obfuscated]:  https://www.preemptive.com/dotfuscator/ce/docs/help/gui_decode_stack_trace.html