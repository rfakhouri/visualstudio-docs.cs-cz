---
title: Hierarchická organizace zdrojů pro lokalizaci
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- resource files, localized
- localization [Visual Studio], resources
- fallback resources
- international applications [Visual Studio], storing resources
- satellite assemblies, resource hierarchies
- globalization [Visual Studio], resources
- satellite assemblies
- resources [Visual Studio], fallback system
- resource files, fallback processes
ms.assetid: dadf8f2c-f74c-44d7-bec0-a1e956d8d38d
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c46fbfe13e7e4c795703a53debedca20ae39c145
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752317"
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Hierarchická organizace zdrojů pro lokalizaci

V sadě Visual Studio jsou uložené v samostatné soubory lokalizované prostředky (například řetězce a bitové kopie, které jsou vhodné pro každou jazykovou verzi data) a načíst podle nastavení jazykové verze uživatelského rozhraní. Zjistit, jak jsou načíst lokalizované prostředky, je vhodné považovat je jako hierarchické uspořádání.

## <a name="kinds-of-resources-in-the-hierarchy"></a>Typy prostředků v hierarchii

-   Nouzové prostředky pro váš výchozí jazykovou verzi, třeba Angličtina ("en"), se nacházejí na nejvyšší úrovni hierarchie. Tyto nouzové prostředky jsou pouze ty, které nemají své vlastní soubor; jsou uložené v hlavní sestavení.

-   V následující tabulce nouzové prostředky jsou prostředky pro všechny neutrální jazykové verze. Neutrální jazykovou verzi je spojeno s jazykem, ale ne na zemi nebo oblast. Francouzština ("fr") je třeba neutrální jazykovou verzi. (Nouzové prostředky jsou také pro neutrální jazykovou verzi, ale speciální jeden).

-   Prostředky pod neutrální jazykovou verzi jsou prostředky pro všechny konkrétní jazykové verze. Konkrétní jazykové verze je přidružen jazyk a na zemi nebo oblast. Francouzština (Kanada) ("fr-CA") je třeba konkrétní jazykové verze.

 Pokud se aplikace pokusí načíst všechny lokalizovaný prostředek, například řetězec a nebyl nalezen, bude cestují u nahoru v hierarchii, dokud nenajde soubor prostředků obsahující požadovaný prostředek.

 Nejlepší způsob, jak ukládat vaše prostředky je generalize je co nejvíce. To znamená, že k uložení lokalizované řetězce, Image, a tak dále v soubory prostředků pro neutrální jazykové verze, nikoli konkrétní jazykové verze, kdykoli je to možné. Například pokud máte prostředky pro belgické francouzština ("fr-být") jazykovou verzi a okamžitě výše uvedené prostředky jsou nouzové prostředky v angličtině, k problému může dojít, když někdo používá aplikace v systému nakonfigurovaný pro francouzštině Kanadští jazykovou verzi. Systém hledá satelitní sestavení pro "fr-CA", ale nelze najít, tak načte hlavní sestavení obsahující záložní prostředků angličtinu, namísto načítání francouzské prostředky. Následující obrázek znázorňuje tuto nežádoucího scénář.

 ![Pouze konkrétní prostředky](../ide/media/vbspecificresourcesonly.gif)

 Pokud dodržíte doporučený postup uvedení množství prostředků nejdříve do souboru neutrální prostředků pro jazykovou verzi "fr", francouzštině Kanadští uživatel nebude vidět prostředky označené pro "fr-být" jazykovou verzi, ale by zobrazit řetězce ve francouzštině. Následující situaci znázorňuje tento upřednostňované scénář.

 ![NeutralSpecificResources – grafika](../ide/media/vbneutralspecificresources.gif)

## <a name="see-also"></a>Viz také:

- [Neutrální jazyky zdrojů pro lokalizaci](../ide/neutral-resources-languages-for-localization.md)
- [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)