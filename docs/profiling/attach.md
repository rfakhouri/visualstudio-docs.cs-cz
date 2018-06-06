---
title: Připojit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 79614283-6733-4592-a53a-d428052271ad
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d227fd84cd14db165ad0253cb7ceefd4f50eb580
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34690624"
---
# <a name="attach"></a>Připojit
*VSPerfCmd.exe* **Attach** možnost začne ukázka profilace z běžící proces zadaný pomocí ID procesu (PID).  
  
 Použít **Attach** možnost, musíte zadat **ukázka** metoda v možnosti spuštění.  
  
> [!NOTE]
>  Pokud **spustit** s byla zadána možnost **Crosssession** možnost, všechny volání **VSPerfCmd /Attach** nebo **VSPerfCmd /Detach** musí zadat také **Crosssession**.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /Attach:ProcessID [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `ProcessID`  
 ID procesu (PID) spuštěné procesu. Identifikátor PID spuštěných procesů je uvedena na kartě procesy ve Správci úloh systému Windows.  
  
## <a name="valid-options"></a>Platné možnosti.  
 Následující **VSPerfCmd** možnosti mohou být kombinovány s **Attach** možnost na jednoho příkazového řádku.  
  
 **Crosssession**  
 Umožňuje profilace – aplikace v relacích než přihlašovací relace. Požadováno pokud **spustit** s byla zadána možnost **Crosssession** možnost.  
  
 **Spusťte:** `Method`  
 Inicializuje relaci příkazového řádku profileru a nastaví zadanou metodu profilování.  
  
 **TargetCLR**  
 Určuje verzi systému rozhraní .NET Framework CLR Common Language Runtime () do profilu při více než jedna verze je načten do relace profilování. Ve výchozím nastavení je první načíst verze profilovaným.  
  
 **GlobalOn GlobalOff**  
 Obnoví (**GlobalOn**) nebo pozastaví (**GlobalOff**) profilace, ale nemá na konci relace profilování.  
  
 **ProcessOn:** `PID` **ProcessOff:** `PID`  
 Obnoví (**ProcessOn**) nebo pozastaví (**ProcessOff**) profilace pro proces zadaný.  
  
## <a name="interval-options"></a>Možnosti intervalu  
 Jeden z následujících možností intervalu vzorkování lze zadat na příkazovém řádku připojit. Výchozí interval vzorkování je 10 000 000 hodinových cyklů procesoru.  
  
 **Časovač**[**:**`Cycles`]**PF**[**:**`Events`]**Sys**[**:** Události]**čítač**[**:**`Name`,`Reload`,`FriendlyName`]  
 Určuje počet a typ intervalu vzorkování.  
  
-   **Časovač** – ukázky každých `Cycles` hodinových cyklů procesoru. Pokud `Cycles` není zadán, jsou používány 10 000 000 cykly.  
  
-   **PF** – ukázky každých `Events` chyby stránek. Pokud `Events` není zadán, jsou používány 10 chyb stránek.  
  
-   **Sys** – ukázky každých `Events` volání operačního systému. Pokud `Events` není zadán, jsou používány 10 systémová volání.  
  
-   **Čítač** – ukázky každých `Reload` počet výkonu procesoru čítač určeného `Name`. Volitelně můžete `FriendlyName` můžete zadejte řetězec, který bude použit jako záhlaví sloupce v sestav profileru.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak připojit k běžící instanci aplikace s ID procesu 12345.  
  
```cmd  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Attach:12345  
```  
  
## <a name="see-also"></a>Viz také:  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)