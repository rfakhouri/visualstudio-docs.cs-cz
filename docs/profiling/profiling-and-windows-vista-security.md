---
title: Profilace a zabezpečení Windows Vista | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: ac83bc523b830c3e3adff258511d2785db0ddb62
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49924795"
---
# <a name="profiling-and-windows-vista-security"></a>Profilace a zabezpečení systému Windows Vista
V závislosti na tom [!INCLUDE[wiprlhext](../debugger/includes/wiprlhext_md.md)] přístupová oprávnění uživatelů nastavení, které správce má k dispozici, individuální uživatel může mít oprávnění zabezpečení, chcete-li Profilovat procesy v tomto počítači. Následující příklady znázorňují možné rozdíly mezi uživateli:  
  
- Někteří uživatelé mohou přístup k rozšířeným funkcím profilace, pokud správce nastavil ovladač a spouštění služby.  
  
- Uživatelé domény mohou přistupovat k pouze profilace vzorku.  
  
- Někteří uživatelé mohou odepřít přístup k profilaci a všem ostatním uživatelům.  
  
  Další informace najdete v tématu Možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profilace mezi relacemi  
 *Mezi relacemi profilace* je schopnost Profilovat proces, na kterém běží v jiné přihlašovací relace. Například většina služeb spuštěné v relaci 0, a uživatelé nemůžou spouštět přímo v relaci 0. S použitím **připojit k procesu** tlačítko na panelu nástrojů prohlížeče výkonu nebo / attach možnost příkazového řádku nástroje VSPerfCmd, můžete provádět profilaci většina procesů v různých přihlašovacích relacích.  
  
 Zobrazí se seznam procesů, které jsou k dispozici nastavením možností profilace viditelnost napříč procesy. Tyto možnosti jsou dostupné v **připojit k procesu** okno, které se zobrazí po kliknutí na **připojit k procesu**:  
  
-   **Zobrazit procesy všech uživatelů**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí pouze procesy, které jsou vlastněny aktuálního uživatele. Když **Zobrazit procesy všech uživatelů** je vybráno, zobrazí se seznam procesy všech uživatelů.  
  
-   **Zobrazit procesy ve všech relacích**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí procesy v aktuální relaci. Pokud je vybraná tato možnost, v seznamu zobrazí procesy ve všech relacích.  
  
## <a name="see-also"></a>Viz také:  
 [Přehledy](../profiling/overviews-performance-tools.md)   
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Postupy: připojení ke spuštěnému procesu](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)