---
title: Spustit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: cf374c03f7918e48c57f221ada22e43b435c0a78
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="start"></a>Spustit
**Spustit** možnost je VSPerfCmd.exe možnost, která inicializuje profileru pro zadanou metodu profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /Start:Method /Output:FileName [Options]  
```  
  
#### <a name="parameters"></a>Parametry  
 `Method`  
 Musí mít jednu z následujících klíčových slov:  
  
-   **TRASOVÁNÍ** -určuje metody instrumentace.  
  
-   **Ukázka** -určuje metody vzorkování.  
  
-   **POKRYTÍ** -určuje pokrytí kódu.  
  
-   **CONCURRENCY** -určuje metodu kolizí prostředku.  
  
## <a name="required-options"></a>Požadované možnosti  
 **Výstup** možnost musí být zadán při **spustit** je zadán v příkazovém řádku.  
  
 **Výstup:** `filename`  
 Určuje název výstupního souboru.  
  
## <a name="exclusive-options"></a>Vylučující možnosti  
 Tyto možnosti lze použít pouze s **spustit** možnost na příkazovém řádku.  
  
 **CrossSession**&#124;**CS**  
 Umožňuje napříč procesem vytváření profilů. Názvy možností **CrossSession** a **CS** jsou obě podporována.  
  
 **Uživatel:**[`domain\`]`username`  
 Umožňuje klientský přístup k monitorování ze zadaného účtu.  
  
 **WinCounter:** `Path` [**pro automatické označování**:`n`]  
 **WinCounter** určuje čítačů výkonu systému Windows má být zahrnut jako značky v profilaci datového souboru. **Pro automatické označování** Určuje interval v milisekundách mezi kolekcí datového souboru.  
  
## <a name="invalid-options"></a>Neplatné možnosti  
 Tyto možnosti nelze použít s **spustit** možnost na příkazovém řádku.  
  
 **Status**  
 **Stav** se vztahují na tyto procesy, které jsou profilovaným. Zobrazí seznam procesy a vláken a jejich aktuální stav profilu (zapnuto nebo vypnuto). Například, pokud proces je zastavena **stav** nebude oznámí v sestavě. **Stav** vám ukáže, že je proces buď profilovaným nebo ne.  
  
 **Vypnutí**[**:**`Timeout`]  
 Vypne profileru.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat VSPerfCmd.exe **spustit** možnost k chybě při inicializaci profileru.  
  
```  
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp  
VSPerfCmd.exe /Launch:TestApp.exe  
```  
  
## <a name="see-also"></a>Viz také  
 [Vsperfcmd –](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)