---
title: "Postupy: shromažďovat trasování událostí pro Windows (ETW) Data | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
ms.assetid: aa2261fe-d5f5-49fc-a171-d18842e1dc7d
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a720bf57c8668d956a1036d73a264a4936142cd4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>Postupy: Shromažďování dat Trasování událostí pro Windows
Události trasování událostí pro Windows (ETW) je zařízení efektivní jádra úroveň trasování, které umožňuje jádra protokolu profileru nebo události definované aplikací. Data, která se shromažďují ze zprostředkovatele událostí lze zobrazit pouze pomocí /**souhrn: ETW** možnost [vsperfreport –](../profiling/vsperfreport.md) nástroj příkazového řádku. Tato sestava slouží k určení, kde dojde k problémům s výkonem v aplikaci.  
  
 **Požadavky**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Funkce Rozšířené zabezpečení v systému Windows 8 a Windows Server 2012 vyžaduje významné změny ve způsobu, jakým Visual Studio profiler shromažďuje data na těchto platformách. Aplikace UWP také vyžadují nové techniky kolekce. V tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-enable-event-trace-providers"></a>Chcete-li povolit zprostředkovatelé trasování událostí  
  
1.  V **prohlížeč výkonu**, klikněte pravým tlačítkem na výkonnostní relace a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **stránky vlastností**, klikněte **události systému Windows** vlastnosti.  
  
3.  V **zprostředkovatel trasování událostí vyberte ke shromažďování dat z** vyberte zprostředkovatelů událostí, které chcete použít pro profil aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace výkonnostních relací](../profiling/configuring-performance-sessions.md)