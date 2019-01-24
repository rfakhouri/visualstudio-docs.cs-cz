---
title: Události (VSPerfCmd) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: eb139327-4783-4f2a-874c-efad377a7be4
caps.latest.revision: 12
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bcfd234f67245ee39e8ba278ec256ba68b158785
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54800168"
---
# <a name="events-vsperfcmd"></a>Události (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

VSPerfCmd.exe **události** možnost řídí protokolování trasování událostí pro Windows (ETW). Data trasování událostí pro Windows jsou uložena do souboru ETL, který je oddělené od datového souboru profilování. Data můžete zobrazit v sestavě pomocí [VSPerfReport](../profiling/vsperfreport.md) příkaz/Summary: ETW.  
  
 **Události** možnost může být volána kdykoli před příkazu vsperfcmd proveďte **vypnutí** příkaz je volána k zastavení profilování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
VSPerfCmd.exe /events {On|Off} {Guid|ProviderName} [,Flags[,Level]  
```  
  
#### <a name="parameters"></a>Parametry  
 **On**&#124;**Off**  
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
  
```  
C:\<path>VSPerfCmd -events on, \".NET Common Language Runtime\", 0x7fffffff, 5  
```  
  
> [!IMPORTANT]
>  Abyste nevylučovali události spuštění, pak vzhledem k tomu, že tyto události nejsou uvedené v souboru formátu MOF (Managed Object) se zobrazí jako identifikátory GUID v sestavě. Další informace najdete v článku na této stránce na webu společnosti Microsoft: [Ukázkové Managed Object Format (MOF) soubor](http://go.microsoft.com/fwlink/?linkid=37118).  
  
## <a name="see-also"></a>Viz také  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [Profilace samostatných aplikací](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [Profilace webových aplikací ASP.NET](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [Profilace služeb](../profiling/command-line-profiling-of-services.md)
