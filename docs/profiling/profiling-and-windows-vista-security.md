---
title: Profilování a zabezpečení systému Windows Vista | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f64483ff7c296e8a428d845018ac9630419c037e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="profiling-and-windows-vista-security"></a>Profilace a zabezpečení systému Windows Vista
V závislosti na tom [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] nastavení přístupová oprávnění uživatelů, které správce počítače má k dispozici, jednotlivého uživatele může mít bezpečnostní oprávnění k profilu proces na tomto počítači. Následující příklady ilustrují možné rozdíly mezi uživateli:  
  
-   Někteří uživatelé mohou pokročilé funkce profilování přístup, až správce nastavil ovladače a spuštění služby.  
  
-   Uživatelé domény může přístup k ukázkové profilace jenom.  
  
-   Někteří uživatelé mohou odepřít přístup k profilace všem ostatním uživatelům.  
  
 Další informace najdete v tématu Možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Relace mezi profilace  
 *Relace mezi profilace* je schopnost profilu proces, který běží v různých přihlašovací relace. Například většina služeb spusťte v relaci 0 a uživatelé nelze spustit přímo v relaci 0. Pomocí **připojit k procesu** tlačítka na panelu nástrojů Prohlížeč výkonu nebo / připojit možnost vsperfcmd – nástroj příkazového řádku, můžete profil většina procesů v různých přihlašovací relace.  
  
 Zobrazí se seznam procesů, které jsou k dispozici nastavením profilování možnostmi viditelnosti mezi procesy. Tyto možnosti jsou dostupné v **připojit k procesu** okno, které se zobrazí po kliknutí na tlačítko **připojit k procesu**:  
  
-   **Zobrazit procesy všech uživatelů**  
  
     Pokud není vybraná tato možnost, zobrazí se seznam pouze procesy, které jsou vlastněny aktuálního uživatele. Když **Zobrazit procesy od všech uživatelů** je vybrána, zobrazí se seznam procesy všech uživatelů.  
  
-   **Zobrazení procesů v všechny relace**  
  
     Pokud není vybraná tato možnost, zobrazí se seznam procesy v aktuální relaci. Pokud je vybraná tato možnost, zobrazí se seznam procesy v všechny relace.  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../profiling/overviews-performance-tools.md)   
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Postupy: připojení ke spuštění procesu](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)