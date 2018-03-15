---
title: "Postupy: použití protokolu aktivit | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9f45e18ebb2ab3e83041ea0e1ba5c2de4c9b8532
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="how-to-use-the-activity-log"></a>Postupy: použití protokolu aktivit
VSPackages může zapisovat zprávy do protokolu činnosti. Tato funkce je užitečná zejména při ladění VSPackages v prostředích prodejní.  
  
> [!TIP]
>  Protokol aktivit je vždy povolena. Visual Studio zachová postupné vyrovnávací paměti poslední 100 záznamů, jakož i prvních 10 položek, které obsahují informace o obecné konfiguraci.  
  
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
  
     Tento kód získá <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> služby a obsahuje ji do <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> rozhraní. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> zapíše informační položku do protokolu činnosti pomocí aktuální kulturního kontextu.  
  
2.  Když VSPackage načtena (obvykle při vyvolání příkazu nebo je-li otevřít okno), je text zapíšou do protokolu aktivit.  
  
### <a name="to-examine-the-activity-log"></a>Chcete-li v protokolu aktivit  
  
1.  Visual Studio s spustit [/Log](../ide/reference/log-devenv-exe.md) přepínač příkazového řádku k zápisu ActivityLog.xml na disk během relace.

2.  Po zavření Visual Studio, najít protokol aktivit v podsložce pro Visual Studio data: *data aplikací %*\Microsoft\VisualStudio\15.0\ActivityLog.xml.  
  
3.  V každém textovém editoru otevřete protokol aktivit. Zde je typické položka:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Robustní programování  
 Protože protokol aktivit je služba, není k dispozici v konstruktoru VSPackage protokolu aktivit.  
  
 Opatřete si protokol aktivit těsně před zápis do něj. Ukládat do mezipaměti nebo uložení protokol aktivit pro budoucí použití.  
  
## <a name="see-also"></a>Viz také
 [/Log (devenv.exe)](../ide/reference/log-devenv-exe.md)   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Řešení potíží s VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [Balíčky VSPackage](../extensibility/internals/vspackages.md)
