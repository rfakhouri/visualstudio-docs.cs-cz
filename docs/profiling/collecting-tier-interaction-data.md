---
title: "Shromažďování dat interakce vrstev | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.tierinteraction
helpviewer_keywords:
- Profiling Tools,ADO.NET profiling
- tier interaction profiling method
- Profiling Tools,tier-interaction method
- ADO.NET performance profiling
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c12d279541e60353a9e6e4354a16870713498b66
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="collecting-tier-interaction-data"></a>Shromažďování dat interakce vrstev
Profilace interakce vrstvy poskytuje další informace o dobu provádění funkcí víceúrovňových aplikací, které komunikují s databází prostřednictvím služeb ADO.NET. Data jsou shromažďována jenom pro funkce synchronní volání.  
  
 **Edice Visual Studio**  
  
 Pomocí nástrojů Visual Studio Ultimate, Visual Studio Premium nebo Visual Studio Professional se můžou shromažďovat profilování dat interakce vrstev. Data profilace sledováním interakce vrstev však lze zobrazit pouze v VS Ultimate a VS Premium.  
  
 **Windows 8 a Windows Server 2012**  
  
 Shromažďování dat interakce vrstev v aplikacích klasické pracovní plochy Windows 8 a Windows Server 2012 aplikace, musíte použít metodu instrumentace. Nelze shromažďování dat interakce vrstev pro aplikace UWP. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md). Můžete zahrnout dat interakce vrstev všechny metody profilování jiné podporované verze systému Windows.  
  
 **Průvodce výkonu**  
  
 Z důvodu chyb v Průvodci výkonu je nutné přidat možnost kolekce dat interakce vrstvy na spuštění profilování z Průzkumníka výkonu. Musíte taky přidat projekt, spustitelný soubor nebo webu do cílového uzlu prohlížeč výkonu.  
  
### <a name="to-add-tier-interaction-data-to-a-profiling-run-by-using-the-performance-session-property-pages"></a>Přidání dat interakce vrstev do profilace spustit pomocí stránky vlastností relace výkonu  
  
1.  V Průzkumníku výkonu, zvolte **vlastnosti** v místní nabídce.  
  
2.  Vyberte **interakcí vrstev** stránky a poté zkontrolujte **povolit profilace interakce vrstvy** zaškrtávací políčko.  
  
3.  V Průzkumníku výkonu, vyberte **cíle** uzel a pak zadejte projektu, spustitelný soubor nebo webový server, který chcete profil.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení interakcí vrstev](../profiling/tier-interactions-view.md)