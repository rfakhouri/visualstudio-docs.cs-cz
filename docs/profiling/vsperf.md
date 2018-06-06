---
title: VSPerf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: b5854e62-279e-4850-bfeb-0c6ef82f4805
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fcac1e902ccc1fcc5432a231c5f34629422815fd
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477389"
---
# <a name="vsperf"></a>VSPerf
Použití **VsPerf** nástroj příkazového řádku:  
  
1.  Profil aplikace UWP z příkazového řádku, když Visual Studio není nainstalována na zařízení.  
  
2.  Profilů aplikací klasické pracovní plochy Windows 8 a Windows Server 2012 aplikace pomocí vzorkování metoda profilování.  
  
 Další informace o vytváření profilů možnosti najdete v tématu [nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="uwp-apps-only"></a>Jenom aplikace UWP  
 Tyto možnosti platí pouze pro aplikace UWP.  
  
|||  
|-|-|  
|**/App: {AppName}.**|Spustí profileru a čeká na zadané aplikaci lze spustit z nabídky Start.<br /><br /> Spustit `vsperf /listapps` Chcete-li zobrazit aplikaci název a PackageFullName nainstalovaných aplikací.|  
|**/ balení: {PackageFullName}**|Spustí profileru a čeká na zadané aplikaci lze spustit z nabídky Start.<br /><br /> Spustit `vsperf /listapps` Chcete-li zobrazit aplikaci název a PackageFullName nainstalovaných aplikací.|  
|**/JS**|Vyžaduje se pro profilace aplikací JavaScript.<br /><br /> Shromažďování dat o výkonu z aplikací jazyka JavaScript.<br /><br /> Použití pouze s /package nebo / připojit.|  
|**/noclr**|Volitelné. Neshromažďují CLR data.<br /><br /> Použití pouze s /package nebo / připojit.<br /><br /> Optimalizace, bude vyřešen žádné spravované symboly.|  
|**/listapps**|Seznam názvů nainstalovanou aplikaci a PackageFullNames.|  
  
## <a name="windows-8-desktop-applications-and-windows-server-2012-applications-only"></a>Aplikací klasické pracovní plochy Windows 8 a pouze aplikací systému Windows Server 2012  
 Tyto možnosti pro aplikace UWP nefungují.  
  
|||  
|-|-|  
|**/ Spusťte: {spustitelný soubor}**|Spustí a začne profilace zadaný spustitelný soubor.|  
|**/args: {ExecutableArguments}**|Určuje argumenty příkazového řádku k předávání **/spusťte** cíl.|  
|**/ Console**|Spustí **/spusťte** cíl v nové příkazové okno.|  
  
## <a name="all-applications"></a>Všechny aplikace  
 Tato možnost platí pro všechny aplikace systému Windows 8 nebo Windows Server 2012.  
  
|||  
|-|-|  
|**/ připojit: {PID&#124;název_procesu} [, PID&#124;název_procesu]...**|Shromažďuje data z určených procesů.<br /><br /> Pomocí Správce úloh můžete zobrazit identifikátor procesu (PID) a zpracovat názvy spuštěných aplikací.|  
|**/ file:{ReportName}**|Volitelné. Určuje výstupní soubor (přepíše existující soubor).<br /><br /> Použití pouze s /package nebo / připojit.|  
|**/ Pause**|Shromažďování dat pozastavení.|  
|**/Resume**|Obnovte data kolekce.|  
|**/ stop**|Zastavte shromažďování dat a ukončit procesy cíl.|  
|**/ Odpojit**|Zastavit shromažďování dat, ale nechat nadále spouštět procesy cíl.|  
|**/ Status**|Zobrazit stav profileru.|  
  
## <a name="see-also"></a>Viz také:  
 [Nástroje pro sledování výkonu v aplikacích pro Windows 8 a Windows Server 2012](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)   
 [Profil z příkazového řádku](../profiling/using-the-profiling-tools-from-the-command-line.md)