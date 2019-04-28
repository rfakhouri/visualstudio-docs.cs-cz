---
title: Profilace a zabezpečení Windows Vista | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Profiling Tools,security
- performance tools, security
ms.assetid: 842112fc-b886-4801-8cd7-a25b314b0393
caps.latest.revision: 24
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: fb95164642595195dc62166aec5c81f39abd33e3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62423115"
---
# <a name="profiling-and-windows-vista-security"></a>Profilace a zabezpečení systému Windows Vista
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V závislosti na tom [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)] přístupová oprávnění uživatelů nastavení, které správce má k dispozici, individuální uživatel může mít oprávnění zabezpečení, chcete-li Profilovat procesy v tomto počítači. Následující příklady znázorňují možné rozdíly mezi uživateli:  
  
- Někteří uživatelé mohou přístup k rozšířeným funkcím profilace, pokud správce nastavil ovladač a spouštění služby.  
  
- Uživatelé domény mohou přistupovat k pouze profilace vzorku.  
  
- Někteří uživatelé mohou odepřít přístup k profilaci a všem ostatním uživatelům.  
  
  Další informace najdete v tématu Možnosti správce v [VSPerfCmd](../profiling/vsperfcmd.md).  
  
## <a name="cross-session-profiling"></a>Profilace mezi relacemi  
 *Mezi relacemi profilace* je schopnost Profilovat proces, na kterém běží v jiné přihlašovací relace. Například většina služeb spuštěné v relaci 0, a uživatelé nemůžou spouštět přímo v relaci 0. S použitím **připojit k procesu** tlačítko na panelu nástrojů prohlížeče výkonu nebo / attach možnost příkazového řádku nástroje VSPerfCmd, můžete provádět profilaci většina procesů v různých přihlašovacích relacích.  
  
 Zobrazí se seznam procesů, které jsou k dispozici nastavením možností profilace viditelnost napříč procesy. Tyto možnosti jsou dostupné v **připojit k procesu** okno, které se zobrazí po kliknutí na **připojit k procesu**:  
  
- **Zobrazit procesy všech uživatelů**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí pouze procesy, které jsou vlastněny aktuálního uživatele. Když **Zobrazit procesy všech uživatelů** je vybráno, zobrazí se seznam procesy všech uživatelů.  
  
- **Zobrazit procesy ve všech relacích**  
  
     Pokud není vybraná tato možnost, v seznamu zobrazí procesy v aktuální relaci. Pokud je vybraná tato možnost, v seznamu zobrazí procesy ve všech relacích.  
  
## <a name="see-also"></a>Viz také  
 [Přehledy](../profiling/overviews-performance-tools.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Postupy: Připojit ke spuštěnému procesu](http://msdn.microsoft.com/636d0a52-4bfd-48d2-89ad-d7b9ca4dc4f4)
