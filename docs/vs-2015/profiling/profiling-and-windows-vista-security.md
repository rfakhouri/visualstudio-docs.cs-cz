---
title: Profilace a zabezpečení Windows Vista | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 736e7a04813a6c56d6cab6d1886171e321d583cb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673623"
---
# <a name="profiling-and-windows-vista-security"></a>Profilace a zabezpečení systému Windows Vista
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [profilace a zabezpečení Windows Vista](https://docs.microsoft.com/visualstudio/profiling/profiling-and-windows-vista-security).  
  
V závislosti na tom [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)] přístupová oprávnění uživatelů nastavení, které správce má k dispozici, individuální uživatel může mít oprávnění zabezpečení, chcete-li Profilovat procesy v tomto počítači. Následující příklady znázorňují možné rozdíly mezi uživateli:  
  
-   Někteří uživatelé mohou přístup k rozšířeným funkcím profilace, pokud správce nastavil ovladač a spouštění služby.  
  
-   Uživatelé domény mohou přistupovat k pouze profilace vzorku.  
  
-   Někteří uživatelé mohou odepřít přístup k profilaci a všem ostatním uživatelům.  
  
 Další informace najdete v tématu Možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profilace mezi relacemi  
 *Mezi relacemi profilace* je schopnost Profilovat proces, na kterém běží v jiné přihlašovací relace. Například většina služeb spuštěné v relaci 0, a uživatelé nemůžou spouštět přímo v relaci 0. S použitím **připojit k procesu** tlačítko na panelu nástrojů prohlížeče výkonu nebo / attach možnost příkazového řádku nástroje VSPerfCmd, můžete provádět profilaci většina procesů v různých přihlašovacích relacích.  
  
 Zobrazí se seznam procesů, které jsou k dispozici nastavením možností profilace viditelnost napříč procesy. Tyto možnosti jsou dostupné v **připojit k procesu** okno, které se zobrazí po kliknutí na **připojit k procesu**:  
  
-   **Zobrazit procesy všech uživatelů**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí pouze procesy, které jsou vlastněny aktuálního uživatele. Když **Zobrazit procesy všech uživatelů** je vybráno, zobrazí se seznam procesy všech uživatelů.  
  
-   **Zobrazit procesy ve všech relacích**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí procesy v aktuální relaci. Pokud je vybraná tato možnost, v seznamu zobrazí procesy ve všech relacích.  
  
## <a name="see-also"></a>Viz také  
 [Přehledy](../profiling/overviews-performance-tools.md)   
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Postupy: připojení ke spuštěnému procesu](http://msdn.microsoft.com/en-us/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)



