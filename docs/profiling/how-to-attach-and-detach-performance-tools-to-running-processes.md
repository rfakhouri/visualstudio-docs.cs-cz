---
title: Připojení nástroje pro měření výkonu ke spuštěným procesům
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.performance.attach
helpviewer_keywords:
- performance tools, attach process
- profiling tools, detach process
- profiling tools, attach process
- performance tools, detach process
- profiler
ms.assetid: 56a99c39-e7f6-4f48-ae56-04ab8e022bf7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 181bcf665ce905bff20f98be19d4a789cfe530c2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63431575"
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>Postupy: Připojení nástrojů pro měření výkonu ke spuštěným procesům a jejich odpojení
Profiler slouží k připojení nebo odpojení od spuštěného procesu pro usnadnění odběru vzorků a shromažďuje data výkonu. Tímto způsobem může Profilovat proces, pokud chcete se vyhnout, shromažďování dat o čas načtení aplikace, nebo k monitorování výkonu procesu po jeho dosažení určitý stav.

> [!NOTE]
> Následující postup se vztahuje k připojení a odpojení procesy v rámci [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] integrované environmnent vývojové (prostředí IDE). Informace o tom, jak pomocí nástrojů příkazového řádku najdete v tématu [profilu z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md). Informace o tom, jak služby profilů najdete v tématu [profilu služby](../profiling/command-line-profiling-of-services.md).

 Procesy, které jsou k dispozici pro profil záviset na oprávnění uživatelského přístupu, které jsou nastaveny správcem počítače. Uživatelský účet může třeba mít oprávnění pro kterýkoli z následujících:

- Pokročilé funkce, profilace, pokud správce nastavil ovladač a spouštění služby.

- Ukázka profilace pouze (uživatelé domény).

- Odepřete přístup k profilaci pro každého.

  Další informace najdete v tématu [profilace a Windows Vista zabezpečení](../profiling/profiling-and-windows-vista-security.md) a možností správy v [VSPerfCmd](../profiling/vsperfcmd.md).

### <a name="to-attach-to-a-running-process"></a>Připojit ke spuštěnému procesu

1. Na **ladění** nabídky, přejděte k **Profiler**, pak **prohlížeč výkonu**a potom klikněte na tlačítko **připojit**.

     **Připojit Profiler k procesu** zobrazí se dialogové okno.

2. Klikněte na název, který chcete připojit k procesu.

3. Klikněte na tlačítko **připojit**.

### <a name="to-detach-from-a-running-process"></a>Chcete-li odpojit od spuštěného procesu

1. n **ladění** nabídky, přejděte k **Profiler**, pak **prohlížeč výkonu**a potom klikněte na tlačítko **odpojit**.

     **Připojit Profiler k procesu** zobrazí se dialogové okno.

2. Klikněte na název image, ze kterého se má odpojit.

3. Klikněte na tlačítko **odpojit**.

## <a name="see-also"></a>Viz také:
- [Řízení shromažďování dat](../profiling/controlling-data-collection.md)
- [Přehled výkonnostní relace](../profiling/performance-session-overview.md)
- [Postupy: Spuštění a ukončení shromažďování dat o výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)
- [Profilace a zabezpečení systému Windows Vista](../profiling/profiling-and-windows-vista-security.md)
- [VSPerfCmd](../profiling/vsperfcmd.md)