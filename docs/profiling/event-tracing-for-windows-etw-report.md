---
title: Trasování událostí pro Windows (ETW) sestavu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Event tracing for Windows profiling report
- ETW profiling report
ms.assetid: 81e88162-b88a-40b6-8b85-a232c8096a47
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf64c2fae940de74978fb2d6c10ce380ed3958d5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630181"
---
# <a name="event-tracing-for-windows-etw-report"></a>Sestava události trasování pro Windows (ETW)
Sestava trasování událostí pro Windows (ETW) obsahuje události trasování událostí pro Windows, které byly zaznamenány během relace výkonu z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nástroje pro profilaci. Data trasování událostí pro Windows se shromažďují v binárním (. *ETL*) soubor.

> [!NOTE]
>  Nelze zobrazit sestavy trasování událostí pro Windows v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní.

- Informace o tom, jak shromažďování trasování událostí pro Windows pomocí nástrojů pro profilaci z [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozhraní najdete v tématu [jak: Shromažďování dat trasování událostí pro Windows (ETW)](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md).

- Informace o tom, jak shromažďovat data trasování událostí pro Windows s použitím [VSPerfCmd](../profiling/vsperfcmd.md) nástroje příkazového řádku, naleznete v tématu [události](../profiling/events-vsperfcmd.md).

- Generování sestavy trasování událostí pro Windows pomocí **VSReport / Summary: ETW** příkazu. Další informace najdete v tématu [VSPerfReport](../profiling/vsperfreport.md).

|Sloupec|Popis|
|------------|-----------------|
|**Časové razítko**|Určuje, kdy došlo k události.|
|**ID procesu**|Identifikuje proces, který událost vyvolal.|
|**ID vlákna**|Identifikuje vlákno, které vygenerovalo událost.|
|**Popis**|Identifikuje zprostředkovatel událostí.|
|**Typ**|Určuje typ události.|
|**Vlastnosti**|Vlastnosti události. Každá událost představuje oddělených čárkou, název hodnota pár, který je uzavřen do závorek.|