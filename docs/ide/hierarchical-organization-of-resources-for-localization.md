---
title: Hierarchická organizace zdrojů pro lokalizaci
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4df50f1336f235d50d7c897deb2450469f9128b8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55038601"
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Hierarchická organizace zdrojů pro lokalizaci

V sadě Visual Studio jsou lokalizované prostředky (data, jako jsou řetězce a Image pro jednotlivé jazykové verze) uložená v samostatných souborech a načíst podle nastavení jazykové verze uživatelského rozhraní. Pochopit, jak jsou načteny lokalizované prostředky, je vhodné popřemýšlet z nich jako uspořádané hierarchické způsobem.

## <a name="kinds-of-resources-in-the-hierarchy"></a>Typy prostředků v hierarchii

- Záložní prostředky pro vaše výchozí jazykovou verzi, třeba Angličtina ("en"), se nacházejí na nejvyšší úrovni hierarchie. Tyto materiály záložního jsou pouze ty, které nemají vlastní soubor. ukládají se v hlavní sestavení.

- Následující materiály záložního prostředků pro všechny neutrální jazykové verze. Neutrální jazykovou verzi je přidružený jazyk, ale ne určitá země nebo oblast. Francouzština ("fr") je například neutrální jazykovou verzi. (Náhradní zdrojů jsou také pro neutrální jazykovou verzi, ale speciální jeden).

- Prostředky jsou pod neutrální jazykové verze prostředků pro jakékoli konkrétní jazykové verze. Konkrétní jazykovou verzi je přidružený jazyk a zemi/oblast. Kanadská francouzština ("fr-CA") je třeba konkrétní jazykovou verzi.

Pokud aplikace se pokouší načíst všechny lokalizovaný prostředek, jako je řetězec a nebyly nalezeny, bude místo hierarchie dokud nenajde soubor prostředků obsahující požadovaný prostředek.

Nejlepší způsob, jak ukládat vaše prostředky se k zobecnění je co největší míře. To znamená, že k ukládání lokalizovaných řetězců, obrázků a tak dále v souborech prostředků neutrální jazykové verze, nikoli konkrétní jazykovou verzi, kdykoli je to možné. Například pokud máte prostředky pro Belgii francouzština ("fr-být") jazykovou verzi a okamžitě výše uvedené materiály záložního prostředků v angličtině, problém může dojít, když někdo v systému nakonfigurovaný pro jazykovou verzi francouzština Kanadské používá vaše aplikace. Systém vyhledá satelitní sestavení pro "fr-CA", ale nedokáže najít, proto načte hlavní sestavení obsahující záložní prostředky, angličtina, namísto načítání francouzské prostředky. Následující obrázek znázorňuje tento scénář nežádoucí.

![Jenom konkrétní prostředky](../ide/media/vbspecificresourcesonly.gif)

Pokud budete postupovat podle doporučený postup uvedení množství prostředků je možné soubor prostředků neutrální pro jazykové verze "fr", Kanadské francouzský uživatel neuvidí prostředky označené pro "fr-být" jazyková verze, ale by řetězců zobrazen ve francouzštině. Následující situace ukazuje tento scénář upřednostňované.

![NeutralSpecificResources – obrázek](../ide/media/vbneutralspecificresources.gif)

## <a name="see-also"></a>Viz také:

- [Neutrální jazyky zdrojů pro lokalizaci](../ide/neutral-resources-languages-for-localization.md)
- [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)
- [Lokalizace aplikací](../ide/localizing-applications.md)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)