---
title: "Hierarchická organizace zdrojů pro lokalizaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 7f52d57d45c0f78a5bd64b16f10c9bb7c2256cd7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="hierarchical-organization-of-resources-for-localization"></a>Hierarchická organizace zdrojů pro lokalizaci
V sadě Visual Studio jsou uložené v samostatné soubory lokalizované prostředky (například řetězce a bitové kopie, které jsou vhodné pro každou jazykovou verzi data) a načíst podle nastavení jazykové verze uživatelského rozhraní. Zjistit, jak jsou načíst lokalizované prostředky, je vhodné považovat je jako hierarchické uspořádání.  
  
## <a name="kinds-of-resources-in-the-hierarchy"></a>Typy prostředků v hierarchii  
  
-   V horní části hierarchii nacházejí nouzové prostředky pro váš výchozí jazykovou verzi, třeba Angličtina ("en"). Toto jsou pouze prostředky, které nemají své vlastní soubor; jsou uložené v hlavní sestavení.  
  
-   V následující tabulce nouzové prostředky jsou prostředky pro všechny neutrální jazykové verze. Neutrální jazykovou verzi je spojeno s jazykem, ale ne na zemi nebo oblast. Francouzština ("fr") je třeba neutrální jazykovou verzi. (Všimněte si, že nouzové prostředky jsou také pro neutrální jazykovou verzi, ale speciální jeden.)  
  
-   V následující tabulce těch, které jsou prostředky pro všechny konkrétní jazykové verze. Konkrétní jazykové verze je přidružen jazyk a na zemi nebo oblast. Francouzština (Kanada) ("fr-CA") je třeba konkrétní jazykové verze.  
  
 Pokud se aplikace pokusí načíst všechny lokalizovaný prostředek, například řetězec a nebyl nalezen, bude cestují u nahoru v hierarchii, dokud nenajde soubor prostředků obsahující požadovaný prostředek.  
  
 Nejlepší způsob, jak ukládat vaše prostředky je generalize je co nejvíce. To znamená, že k uložení lokalizované řetězce, Image, a tak dále v soubory prostředků pro neutrální jazykové verze, nikoli konkrétní jazykové verze, kdykoli je to možné. Například pokud máte prostředky pro belgické francouzština ("fr-být") jazykovou verzi a okamžitě výše uvedené prostředky jsou nouzové prostředky v angličtině, k problému může dojít, když někdo používá aplikace v systému nakonfigurovaný pro francouzštině Kanadští jazykovou verzi. Systém nebude hledat satelitní sestavení pro "fr-CA", ji najít a načíst hlavní sestavení obsahující záložní prostředku, který je angličtina, namísto načítání francouzské prostředky. Následující obrázek znázorňuje tuto nežádoucího scénář.  
  
 ![Pouze konkrétní prostředky](../ide/media/vbspecificresourcesonly.gif "vbSpecificResourcesOnly")  
  
 Pokud dodržíte doporučený postup uvedení množství prostředků nejdříve do souboru neutrální prostředků pro jazykovou verzi "fr", francouzštině Kanadští uživatel nebude vidět prostředky označené pro "fr-být" jazyková verze, ale, ale by nezobrazí řetězce ve francouzštině. Následující situaci znázorňuje tento upřednostňované scénář.  
  
 ![NeutralSpecificResources – grafika](../ide/media/vbneutralspecificresources.gif "vbNeutralSpecificResources")  
  
## <a name="see-also"></a>Viz také  
 [Neutrální jazyky zdrojů pro lokalizaci](../ide/neutral-resources-languages-for-localization.md)   
 [Zabezpečení a lokalizovaná satelitní sestavení](../ide/security-and-localized-satellite-assemblies.md)   
 [Lokalizace aplikací](../ide/localizing-applications.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)   
 [Postupy: nastavení jazykové verze a jazyková verze uživatelského rozhraní pro globalizace Windows Forms](http://msdn.microsoft.com/en-us/694e049f-0b91-474a-9789-d35124f248f0)   
 [Postupy: nastavení jazykové verze a jazyková verze uživatelského rozhraní pro globalizaci webové stránky ASP.NET](http://msdn.microsoft.com/Library/76091f86-f967-4687-a40f-de87bd8cc9a0)