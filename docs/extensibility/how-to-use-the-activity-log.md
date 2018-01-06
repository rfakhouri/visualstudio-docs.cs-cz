---
title: "Postupy: použití protokolu aktivit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c27934d043a067f88bd9f47efe7d8f7972959e10
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-activity-log"></a>Postupy: použití protokolu aktivit
VSPackages může zapisovat zprávy do protokolu činnosti. Tato funkce je užitečná zejména při ladění VSPackages v prostředích prodejní.  
  
> [!TIP]
>  Protokol aktivit je vždy povolena. Visual Studio zachová postupné vyrovnávací paměti sto poslední položky, jakož i prvních deset položky, které obsahují informace o obecné konfiguraci.  
  
### <a name="to-write-an-entry-to-the-activity-log"></a>Pro zápis záznamu do protokolu činnosti  
  
1.  Vložte tento kód v <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> metoda nebo v jakékoliv jiné metody, s výjimkou konstruktor VSPackage:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Tento kód získá <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> služby a obsahuje ji do <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A>zapíše informační položku do protokolu činnosti pomocí aktuální kulturního kontextu.  
  
2.  Když VSPackage načtena (obvykle při vyvolání příkazu nebo je-li otevřít okno), je text zapíšou do protokolu aktivit.  
  
### <a name="to-examine-the-activity-log"></a>Chcete-li v protokolu aktivit  
  
1.  Najít protokol aktivit v podsložce pro Visual Studio data: *data aplikací %*\Microsoft\VisualStudio\15.0\ActivityLog.XML...  
  
2.  V každém textovém editoru otevřete protokol aktivit. Zde je typické položka:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Robustní programování  
 Protože protokol aktivit je služba, není k dispozici v konstruktoru VSPackage protokolu aktivit.  
  
 Opatřete si protokol aktivit těsně před zápis do něj. Ukládat do mezipaměti nebo uložení protokol aktivit pro budoucí použití.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Řešení potíží s VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
