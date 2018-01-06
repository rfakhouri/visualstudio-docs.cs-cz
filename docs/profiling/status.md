---
title: Stav | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba656fa4-ef9d-4d8c-a3b6-739c3b5d23ae
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: d1168fb27330f49a714e64478fc7ab167569dadb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="status"></a>Stav
VSPerfCmd.exe **stav** možnost zobrazí informace o stavu profileru a žádné procesy, které jsou aktuálně profilovaný.  
  
 **Stav** možnost musí být pouze možnost zadat na příkazovém řádku. Profileru musí být inicializován s VSPerfCmd.exe **spustit** možnost předtím, než lze zobrazit všechny stavu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Status  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="remarks"></a>Poznámky  
 **Stav** možnost zobrazí následující informace o stavu pro profileru.  
  
 **Název výstupního souboru**  
 Název a cesta k souboru aktuální datový soubor profileru.  
  
 **Režim kolekce**  
 Ukázka nebo trasování  
  
 **Maximální procesy**  
 Maximální počet procesů, které může být najednou profilovaným a počet aktuálně aktivních procesů.  
  
 **Maximální vláken**  
 Maximální počet vláken, která může být profilovaným najednou.  
  
 **Počet vyrovnávacích pamětí**  
 Počet vyrovnávacích pamětí, které jsou vyhrazené pro data profilování zápis.  
  
 **Velikost vyrovnávací paměti**  
 Velikost v bajtech vyrovnávací paměti.  
  
 **Stav** možnost zobrazí následující informace o stavu pro každý proces, který je aktuálně profilovaný.  
  
 **Proces**  
 Název procesu PROFILOVANÉHO.  
  
 **ID procesu**  
 Identifikátor systému procesu.  
  
 **Počet vláken**  
 Počet vláken, které jsou aktuálně spuštěné.  
  
 **Spuštění a zastavení počet**  
 Počet primární interní profileru k řízení shromažďování dat pro tento proces. Počet musí být jednu shromažďovat data. Počet spuštění a zastavení smí uživatel manipulovat profileru rozhraní API a možnosti VSPerfCmd **GlobalOn**, **GlobalOff**, **ProcessOn**, **ProcessOff**, **ThreadOn**, a **ThreadOff**.  
  
 **Pozastavení nebo obnovení činnosti počet**  
 Počet sekundárních interní profileru k řízení shromažďování dat pro tento proces. Počet musí být menší než nebo rovný nule shromažďovat data. **Pozastavit nebo obnovit** počet smí uživatel manipulovat pouze profileru rozhraní API.  
  
 **Uživatelé s přístupovými právy k monitorování**  
 Uvádí jména uživatelů, kteří mají přístup k profileru. Další uživatele je možné udělit přístup pomocí VSPerfCmd.exe **správce** možnost  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)