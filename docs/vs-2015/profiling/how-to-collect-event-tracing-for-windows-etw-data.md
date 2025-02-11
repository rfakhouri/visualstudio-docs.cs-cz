---
title: 'Postupy: Shromažďování trasování událostí pro Windows (ETW) Data | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
ms.assetid: aa2261fe-d5f5-49fc-a171-d18842e1dc7d
caps.latest.revision: 31
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9d113a32622c40c68a030fdbc670ec19c6038de2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432823"
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Postupy: Shromažďovat události trasování pro Windows (ETW) dat.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Event Tracing for Windows (ETW) je efektivní sledování na úrovni jádra zařízení, která umožňuje profileru jádra protokolu nebo události definované aplikací. Data, která se shromažďují ze zprostředkovatele událostí může zobrazit pouze pomocí /**Summary: ETW** možnost [VSPerfReport](../profiling/vsperfreport.md) nástroj příkazového řádku. Tato sestava slouží k určení, kdy dojde k problémům s výkonem v aplikaci.  
  
 **Požadavky**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
> Rozšířené funkce zabezpečení v systému Windows 8 a Windows Server 2012 vyžadují významné změny ve způsobu, jakým profiler systému Visual Studio na těchto platformách shromažďuje data. Aplikace Windows Store také vyžadují nové techniky kolekce. Zobrazit [nástroje pro výkon v aplikacích Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-enable-event-trace-providers"></a>Povolení zprostředkovatelé trasování událostí  
  
1. V **prohlížeč výkonu**, klikněte pravým tlačítkem na relaci výkonu a pak klikněte na tlačítko **vlastnosti**.  
  
2. V **stránky vlastností**, klikněte na tlačítko **události Windows** vlastnosti.  
  
3. V **vyberte poskytovatel trasování pro shromažďování dat z** vyberte zprostředkovatele událostí, které chcete použít pro profilování aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)
