---
title: 'Postupy: Použití protokolu aktivit | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 30
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 812862c3eaf99b7459bb422e174f8fe155ea384a
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60042584"
---
# <a name="how-to-use-the-activity-log"></a>Postupy: Použití protokolu aktivit
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Rozšíření VSPackages můžete zapisovat zprávy do protokolu aktivit. Tato funkce je zvláště užitečné pro ladění rozšíření VSPackages v prostředí maloobchodu.  
  
> [!TIP]
>  Protokol aktivit je vždycky zapnuté. Postupné vyrovnávací paměti sto poslední položky, jakož i prvních deseti položky, které mají informace o obecné konfiguraci udržuje Visual Studio.  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>Zapsat položku do protokolu aktivit  
  
1. Vložte tento kód v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda nebo v jakékoliv jiné metody, s výjimkou VSPackage konstruktor:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Tento kód získá <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> služby a přetypování na <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> zapíše informační položku do protokolu aktivit v kontextu aktuální jazykové verze.  
  
2. Při načítání sady VSPackage (obvykle při vyvolání příkazu nebo se otevře okno) textu se zapíše do protokolu aktivit.  
  
### <a name="to-examine-the-activity-log"></a>Prozkoumat v protokolu aktivit  
  
1. Najít v protokolu aktivit v podsložce pro Visual Studio data: *% AppData %* \Microsoft\VisualStudio\14.0\ActivityLog.XML...  
  
2. Otevřete protokol aktivit pomocí libovolného textového editoru. Zde je typický položka:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Robustní programování  
 Protože protokol aktivit je služba, není k dispozici v konstruktoru VSPackage protokolu aktivit.  
  
 Protokol aktivit by si měly opatřit pouze před zápisem do něj. Ukládat do mezipaměti nebo uložení protokolu aktivit pro budoucí použití.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Řešení potíží s rozšířením VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
