---
title: "Spusťte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3b8a584e8e024416ec9c3feca63297eed4497624
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="launch"></a>Spuštění
**Spusťte** možnost spustí pomocí metody vzorkování profileru a začne zadané aplikace.  
  
 Použít **spusťte** možnost, musíte zadat **ukázka** metoda v **spustit** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `AppName`  
 Název aplikace spustit. Jsou podporovány úplné a částečné cesty z aktuálního adresáře.  
  
## <a name="valid-options"></a>Platné možnosti.  
 Následující možnosti VSPerfCmd mohou být kombinovány s **spusťte** možnost na jednoho příkazového řádku.  
  
 **Začátek:**`Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadanou metodu profilování.  
  
 **GlobalOn**a **GlobalOff**  
 Obnoví (**GlobalOn**) nebo pozastaví (**GlobalOff**) profilace, ale nemá na konci relace profilování.  
  
 **ProcessOn:** `PID` a **ProcessOff**:`PID`  
 Obnoví (**ProcessOn**) nebo pozastaví (**ProcessOff**) profilace pro proces zadaný.  
  
 **TargetCLR**  
 Určuje verzi systému rozhraní .NET Framework CLR Common Language Runtime () do profilu při více než jedna verze je načten do relace profilování. Ve výchozím nastavení je první načíst verze profilovaným.  
  
## <a name="exclusive-options"></a>Vylučující možnosti  
 Tyto možnosti lze použít pouze s **spusťte** možnost.  
  
 **Console**  
 Spustí zadaný aplikace příkazového řádku v novém okně.  
  
 **Argumenty:**`ArgList`  
 Určuje seznam argumentů, které mají být předána do aplikace.  
  
 **LineOff**  
 Zakáže shromažďování dat profilování úrovni řádků.  
  
## <a name="sampling-options"></a>Možnosti vzorkování  
 Na možné zadat jednu z následujících možností intervalu vzorkování **spusťte** příkazového řádku. Výchozí interval vzorkování je 10 000 000 hodinových cyklů procesoru.  
  
 **Časovač**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`] **Čítač**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**přidělení**&#124; **Doba platnosti**]  
 Určuje počet a typ intervalu vzorkování.  
  
-   **Časovač** – ukázky každých `Cycles` cyklů procesoru Zastavit hodiny. Pokud `Cycles` není zadán, jsou používány 10 000 000 cykly.  
  
-   **PF** – ukázky každých `Events` chyby stránek. Pokud `Events` není zadán, 10 chyby stránek.  
  
-   **Sys** – ukázky každých `Events` volání operačního systému. Pokud `Events` není zadán, jsou používány 10 systémová volání.  
  
-   **Čítač** – ukázky každých `Reload` počet výkonu procesoru čítač určeného `Name`. Volitelně můžete `FriendlyName` můžete zadejte řetězec, který bude použit jako záhlaví sloupce v sestav profileru.  
  
-   **Globální Katalog** – data paměti shromažďuje .NET. Ve výchozím nastavení (**přidělení**), data jsou shromažďována v každé události přidělení paměti. Když **životnost** je zadán parametr, data jsou shromažďována také v každé události kolekce paměti.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje použití **spusťte** ke spuštění aplikace.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)