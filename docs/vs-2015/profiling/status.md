---
title: Stav | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3f64364caf914c030fef806c5ae17e90a8368fa3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157790"
---
# <a name="status"></a>Stav
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe **stav** možnost zobrazí informace o stavu profileru a všechny procesy, které jsou právě profilována.  
  
 **Stav** možnost musí být zadán v příkazovém řádku jedinou možností. Profiler je nutné inicializovat s VSPerfCmd.exe **Start** možnost před zobrazením libovolný stav.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Status  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádný  
  
## <a name="remarks"></a>Poznámky  
 **Stav** možnost se zobrazí následující informace o stavu pro profiler.  
  
 **Název výstupního souboru**  
 Název a cesta k souboru aktuální datového souboru profilování.  
  
 **Režim kolekce**  
 UKÁZKOVÝ nebo trasování  
  
 **Maximum procesů**  
 Maximální počet procesů, které jde Profilovat najednou a počet aktuálně aktivních procesů.  
  
 **Maximální počet vláken**  
 Maximální počet vláken, které jde Profilovat najednou.  
  
 **Počet vyrovnávacích pamětí**  
 Počet vyrovnávacích pamětí, které jsou vyhrazené pro zápis dat profilování.  
  
 **Velikost vyrovnávací paměti**  
 Velikost v bajtech vyrovnávací paměti.  
  
 **Stav** možnost se zobrazí následující informace o stavu pro každý proces, který je právě profilována.  
  
 **Proces**  
 Název profilovaný proces.  
  
 **ID procesu**  
 Identifikátor systému procesu.  
  
 **Počet vláken**  
 Počet vláken v tuto chvíli.  
  
 **Počet operací spustit/zastavit**  
 Počet primární interní profiler k řízení shromažďování dat pro tento proces. Počet musí být rovna jedné shromažďovat data. Počet operací spustit/zastavit lze ovládat pomocí rozhraní API profileru a možnosti, VSPerfCmd **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn**, a **ThreadOff**.  
  
 **Počet operací pozastavit/pokračovat**  
 Počet sekundárních interní profiler řízení shromažďování dat pro tento proces. Počet musí být menší než nebo rovna hodnotě nula, pokud chcete shromažďovat data. **Pozastavit/Pokračovat** počet může být používán pouze rozhraní API profileru.  
  
 **Uživatelé s přístupovými oprávněními k monitoru**  
 Obsahuje seznam uživatelů, kteří mají přístup k profileru. Další uživatelé lze udělit přístup pomocí VSPerfCmd.exe **správce** možnost  
  
## <a name="see-also"></a>Viz také  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
