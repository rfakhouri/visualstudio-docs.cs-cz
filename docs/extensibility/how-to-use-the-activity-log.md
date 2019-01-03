---
title: 'Postupy: Použití protokolu aktivit | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9305cf1de6cadc2230b90723ac0f995b425ba3a5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53990331"
---
# <a name="how-to-use-the-activity-log"></a>Postupy: Použití protokolu aktivit
Rozšíření VSPackages můžete zapisovat zprávy do protokolu aktivit. Tato funkce je zvláště užitečné pro ladění rozšíření VSPackages v prostředí maloobchodu.  
  
> [!TIP]
>  Protokol aktivit je vždycky zapnuté. Postupné vyrovnávací paměti posledních 100 položek, jakož i prvních 10 položek, které mají informace o obecné konfiguraci udržuje Visual Studio.  
  
## <a name="to-write-an-entry-to-the-activity-log"></a>Zapsat položku do protokolu aktivit  
  
1.  Vložte tento kód v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda nebo v jakékoliv jiné metody, s výjimkou VSPackage konstruktor:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Tento kód získá <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> služby a přetypování na <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> zapíše informační položku do protokolu aktivit v kontextu aktuální jazykové verze.  
  
2.  Při načítání sady VSPackage (obvykle při vyvolání příkazu nebo se otevře okno) textu se zapíše do protokolu aktivit.  
  
## <a name="to-examine-the-activity-log"></a>Prozkoumat v protokolu aktivit  
  
1. Spuštění sady Visual Studio s [/Log](../ide/reference/log-devenv-exe.md) přepínač příkazového řádku ActivityLog.xml zapsat na disk během vaší relace.

2. Po zavření sady Visual Studio, vyhledejte protokol aktivit v podsložce pro Visual Studio data:  <em>*% AppData %</em>\Microsoft\VisualStudio\15.0\ActivityLog.xml*.  
  
3. Otevřete protokol aktivit pomocí libovolného textového editoru. Zde je typický položka:  
  
   ```  
   Called for: Company.MyApp.MyAppPackage ...  
   ```  
  
## <a name="robust-programming"></a>Robustní programování  
 Protože protokol aktivit je služba, není k dispozici v konstruktoru VSPackage protokolu aktivit.  
  
 Protokol aktivit by si měly opatřit pouze před zápisem do něj. Ukládat do mezipaměti nebo uložení protokolu aktivit pro budoucí použití.  
  
## <a name="see-also"></a>Viz také:
 [/Log (devenv.exe)](../ide/reference/log-devenv-exe.md)   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Řešení potíží s rozšířením VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
