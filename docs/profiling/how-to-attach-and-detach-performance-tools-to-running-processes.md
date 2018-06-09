---
title: 'Postupy: připojení a odpojení nástroje pro sledování výkonu ke spuštěným procesům | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ea9b35192eb2584f92856e5ab9c50eac22da85f7
ms.sourcegitcommit: 269b55b413d2c82e6aa56c6ab8e53da7926fb2e8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/08/2018
ms.locfileid: "35237224"
---
# <a name="how-to-attach-and-detach-performance-tools-to-running-processes"></a>Postupy: připojení a odpojení nástroje pro sledování výkonu ke spuštěným procesům
Profileru lze připojit k nebo odebrat ze spuštěných procesů usnadnění vzorkování a shromáždit data výkonu. Tuto metodu můžete použít k profilu procesu, když budete chtít vyhnout shromažďování dat o čas načítání aplikace nebo sledovat výkon proces po jeho dosáhne určitý stav.  
  
> [!NOTE]
>  Následující postup se vztahuje k připojení a odpojení procesy uvnitř [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] integrované environmnent vývoj (IDE). Informace o tom, jak pomocí nástroje příkazového řádku najdete v tématu [profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md). Informace o tom, jak profilu služby najdete v tématu [profilu služby](../profiling/command-line-profiling-of-services.md).  
  
 Procesy, které jsou k dispozici pro profil závisí na přístupová oprávnění uživatelů, které nastavil správce počítače. Uživatelský účet, třeba mít oprávnění pro některé z následujících:  
  
-   Rozšířené profilace funkce, když správce nastavil ovladače a spuštění služby.  
  
-   Ukázka profilace jenom (uživatelé domény).  
  
-   Odepřít přístup k profilace pro každého.  
  
 Další informace najdete v tématu [profilování a Windows Vista zabezpečení](../profiling/profiling-and-windows-vista-security.md) a možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
### <a name="to-attach-to-a-running-process"></a>Pro připojení k spuštěných procesů  
  
1.  Na **ladění** nabídky, přejděte na příkaz **profileru**, pak **prohlížeč výkonu**a potom klikněte na **Attach**.    
  
     **Připojit profileru proces** zobrazí se dialogové okno.  
  
2.  Klikněte na název procesu, který chcete přiřadit.  
  
3.  Klikněte na tlačítko **připojit**.  
  
### <a name="to-detach-from-a-running-process"></a>K odpojení od spuštěných procesů  
  
1.  n **ladění** nabídky, přejděte na příkaz **profileru**, pak **prohlížeč výkonu**a potom klikněte na **odpojení**. 
  
     **Připojit profileru proces** zobrazí se dialogové okno.  
  
2.  Klikněte na název bitové kopie, ze kterého chcete odpojit.  
  
3.  Klikněte na tlačítko **odpojit**.  
  
## <a name="see-also"></a>Viz také:  
 [Řízení shromažďování dat](../profiling/controlling-data-collection.md)   
 [Přehled výkonnostní relace](../profiling/performance-session-overview.md)   
 [Postupy: spuštění a ukončení shromažďování dat výkonu](../profiling/how-to-start-and-end-performance-data-collection.md)   
 [Profilace a zabezpečení systému Windows Vista](../profiling/profiling-and-windows-vista-security.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)