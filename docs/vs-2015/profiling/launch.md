---
title: Spuštění | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f81bde5c-3394-4b79-a315-c2f6491689b3
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 97ccdd3bf5e78af277430be1d86a95fad2f180e8
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54778925"
---
# <a name="launch"></a>Spuštění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

**Spuštění** možnost spuštění pomocí metody vzorkování profileru a také začne zadané aplikace.  
  
 Použít **spuštění** možnost, je nutné zadat **ukázka** metoda ve **Start** možnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Launch:AppName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `AppName`  
 Název aplikace spustit. Úplné a částečné cesty z aktuálního adresáře. jsou podporovány.  
  
## <a name="valid-options"></a>Platné možnosti  
 Následující možnosti VSPerfCmd je možné kombinovat s **spuštění** možnost v jednom příkazovém řádku.  
  
 **Spusťte:** `Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadané metodě profilování.  
  
 **GlobalOn** a **GlobalOff**  
 Obnoví (**GlobalOn**) nebo pozastavení (**GlobalOff**) profilace, ale nemá na konci relace profilování.  
  
 **ProcessOn:** `PID` a **ProcessOff**:`PID`  
 Obnoví (**ProcessOn**) nebo pozastavení (**ProcessOff**) profilace pro zadaný proces.  
  
 **TargetCLR**  
 Určuje verzi nástroje rozhraní .NET Framework CLR Common Language Runtime () do profilu načtena více než jedna verze v relaci profilování. Ve výchozím nastavení je Profilovat první načtené verze.  
  
## <a name="exclusive-options"></a>Výhradní možnosti  
 Tyto možnosti lze použít pouze s **spuštění** možnost.  
  
 **Console**  
 Spustí zadaný aplikace příkazového řádku v novém okně.  
  
 **Argumenty:** `ArgList`  
 Určuje seznam argumentů pro předání do aplikace.  
  
 **LineOff**  
 Zakazuje shromažďování dat profilování úrovně řádku.  
  
## <a name="sampling-options"></a>Možnosti vzorkování  
 Na lze zadat jedno z následujících možností interval vzorkování **spuštění** příkazového řádku. Výchozí interval vzorkování je 10 000 000 hodinových cyklů procesoru.  
  
 **Timer**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:**`Events`]**Counter**[**:**`Name`,`Reload`,`FriendlyName`]**GC**[:**allocation**&#124;**lifetime**]  
 Určuje počet a typ intervalu vzorkování.  
  
-   **Časovač** – ukázky každý `Cycles` procesoru nepřerušených hodinových cyklů. Pokud `Cycles` není zadán, 10 000 000 cykly se používají.  
  
-   **PF** – ukázky každý `Events` chyby stránek. Pokud `Events` není zadán, 10 chyby stránek.  
  
-   **Sys** – ukázky každý `Events` volání do operačního systému. Pokud `Events` není zadán, 10 volání systému se používají.  
  
-   **Čítač** – ukázky každý `Reload` počet výkon procesoru čítač určené `Name`. Volitelně můžete `FriendlyName` můžete zadejte řetězec, který se použije jako záhlaví sloupce v sestavy profileru.  
  
-   **Uvolňování paměti** – data paměti .NET shromažďuje. Ve výchozím nastavení (**přidělení**), data se shromažďují v každé události přidělení paměti. Když **životnost** parametr zadán, data se shromažďují také na všechny události uvolňování paměti kolekce.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje použití **spuštění** ke spuštění aplikace.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
