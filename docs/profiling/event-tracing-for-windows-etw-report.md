---
title: "Trasování událostí pro Windows (ETW) sestavu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6ae3b43f300ce410f58dd3fc4d849b2fe1bb3c38
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="event-tracing-for-windows-etw-report"></a>Trasování událostí pro Windows – sestava
Trasování událostí pro Windows (ETW) sestava uvádí události trasování událostí pro Windows, které nebyly zaznamenány v relaci výkonu z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástrojích pro profilaci. Trasování událostí pro Windows data jsou shromažďována v souboru binárního souboru (ETL).  
  
> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní.  
  
-   Informace o tom, jak shromažďovat trasování událostí pro Windows pomocí nástrojů pro profilaci z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní najdete v tématu [postup: Data shromažďovat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).  
  
-   Informace o tom, jak shromažďování dat trasování událostí pro Windows pomocí [VSPerfCmd](../profiling/vsperfcmd.md) nástroje příkazového řádku najdete v části [události](../profiling/events-vsperfcmd.md).  
  
-   Vygenerování sestavy trasování událostí pro Windows pomocí **VSReport / souhrn: ETW** příkaz. Další informace najdete v tématu [vsperfreport –](../profiling/vsperfreport.md).  
  
|Sloupec|Popis|  
|------------|-----------------|  
|**Časové razítko**|Určuje, kdy se událost došlo k chybě.|  
|**ID procesu**|Identifikuje proces, který vygeneruje událost.|  
|**ID podprocesu**|Identifikuje vlákno, které vygenerovalo událost.|  
|**Popis**|Identifikuje událostí zprostředkovatele.|  
|**Typ**|Určuje typ události.|  
|**Vlastnosti**|Vlastnosti události. Každá událost je dvojici oddělených čárkami, název hodnota, která je uzavřený v závorkách.|