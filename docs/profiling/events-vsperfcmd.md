---
title: Události (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1b8d6085f21035408b33b229220e4aea10b2b6c5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842080"
---
# <a name="events-vsperfcmd"></a>Události (VSPerfCmd)
*VSPerfCmd.exe* **události** možnost řídí protokolování trasování událostí pro Windows (ETW). Data trasování událostí pro Windows jsou uložena do souboru ETL, který je oddělené od datového souboru profilování. Data můžete zobrazit v sestavě pomocí [VSPerfReport](../profiling/vsperfreport.md) příkaz/Summary: ETW.  
  
 **Události** možnost může být volána kdykoli před příkazu vsperfcmd proveďte **vypnutí** příkaz je volána k zastavení profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```cmd  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametry  
 **Na**&#124;**vypnuto**  
 Spuštění nebo zastavení shromažďování dat událostí.  
  
 `Guid`  
 Identifikátor GUID zprostředkovatele ovládacího prvku.  
  
 `ProviderName`  
 Název zprostředkovatele, který je registrován s Windows Management Instrumentation (WMI).  
  
 `Flags`  
 "0 x"-předponou hexadecimální hodnotu, která je definována poskytovatelem událostí.  
  
 `Level`  
 Určuje objem dat shromážděných. `Level` je definována zprostředkovatel událostí.  
  
 **Události** možnost rozumí následující jádra klíčová slova jako názvy zprostředkovatelů:  
  
 **Proces**  
 Zpracování událostí  
  
 **vlákno**  
 Události vláken  
  
 **Obrázek**  
 Obrázek zatížení a uvolnění události  
  
 **Disk**  
 Události disku vstupně-výstupních operací  
  
 **File**  
 Vstupně výstupní události souboru  
  
 **Hardfault**  
 Hardwarových chyb stránky  
  
 **Pagefault**  
 Obnovitelně stránkování  
  
 **Sítě**  
 Události sítě  
  
 **Registru**  
 Události přístupu k registru  
  
 Všimněte si, že zprostředkovatel jádra jde Povolit jenom. Nejde vypnout, ani je její příznaky možné upravit, dokud se vypne sledování.  
  
## <a name="remarks"></a>Poznámky  
  
> [!NOTE]
>  Pokud jsou povolené událostí CLR ETW, další spuštění data se shromažďují také v sestavě zobrazení trasování. Události spuštění vyloučit z uvedených v sestavě, použijte následující příkaz:  
  
```cmd  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Abyste nevylučovali události spuštění, pak vzhledem k tomu, že tyto události nejsou uvedené v souboru formátu MOF (Managed Object) se zobrazí jako identifikátory GUID v sestavě. Další informace najdete v článku na této stránce na webu společnosti Microsoft: [Ukázkový soubor formátu MOF (Managed Object)](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Viz také:  
 [Nástroj VSPerfCmd](../profiling/vsperfcmd.md)   
 [Samostatné aplikace profilu](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Webové aplikace ASP.NET profilu](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profil služby](../profiling/command-line-profiling-of-services.md)