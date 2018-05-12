---
title: 'Postupy: Úprava souborů Web.Config za účelem instrumentace a profilování dynamicky kompilovaných webových aplikací ASP.NET | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a92e5692-2183-4ae3-9431-b067c6a7aab4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: b21a4916e9e8398096e239ca1736238b0ffe8145
ms.sourcegitcommit: 046a9adc5fa6d6d05157204f5fd1a291d89760b7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/11/2018
---
# <a name="how-to-modify-webconfig-files-to-instrument-and-profile-dynamically-compiled-aspnet-web-applications"></a>Postupy: Úprava souborů Web.Config za účelem instrumentace a profilování dynamicky kompilovaných webových aplikací ASP.NET
Můžete použít [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] metody instrumentace nástrojích pro profilaci ke shromažďování podrobných dat časování, data přidělení paměti .NET a životnosti objektů .NET z dynamicky kompilovat [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace.  
  
 Toto téma popisuje, jak upravte konfigurační soubor web.config. Chcete-li povolit instrumentace a profilování z [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace.  
  
> [!NOTE]
>  Není nutné upravit soubor web.config, když používáte metoda profilování se vzorkováním, nebo když chcete instrumentace předem kompilovaném [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] modulu.  
  
 Kořenovém souboru web.config je **konfigurace** elementu. Instrumentace a profilu dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webovou aplikaci, musíte přidat nebo upravit následující prvky:  
  
-   A **konfigurace/runtime nebo assemblybinding – / dependentAssembly** element, který identifikuje Microsoft.VisualStudio.Enterprise.ASPNetHelper sestavení, které řídí profilace. **DependentAssembly** element obsahuje dva podřízené elementy: **assemblyIdentity** a **základu kódu**.  
  
-   A **configuration/system.web/compilation** element, který identifikuje profileru po zpracování kompilační krok pro cíl sestavení.  
  
-   Dva **přidat** prvky, které identifikují umístění profilace nástrojům jsou přidány do **konfigurace/appSettings** části.  
  
 Doporučujeme vám, že vytvoříte kopii původního souboru web.config, který můžete použít k obnovení konfigurace aplikace.  
  
### <a name="to-add-the-aspnethelper-assembly-as-a-configurationruntimeassemblybindingdependentassembly-element"></a>Chcete-li přidat sestavení ASPNetHelper jako konfigurace/runtime nebo assemblybinding – / dependentAssembly – element  
  
1.  V případě potřeby přidejte **runtime** prvku jako podřízeného prvku **konfigurace** element; jinak, přejděte k dalšímu kroku.  
  
     **Runtime** element nemá žádné atributy. **Konfigurace** element může mít jen jeden **runtime** podřízený element.  
  
2.  V případě potřeby přidejte **assemblybinding –** prvku jako podřízeného prvku **runtime** element; jinak, přejděte k dalšímu kroku.  
  
     **Runtime** element může mít jen jeden **assemblybinding –** elementu.  
  
3.  Přidejte následující atribut název a hodnotu **assemblybinding –** element:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**atribut xmlns**|**název urn: schémata-microsoft-com:asm.v1**|  
  
4.  Přidat **dependentAssembly** prvku jako podřízeného prvku **assemblybinding –** elementu.  
  
     **DependentAssembly** element nemá žádné atributy.  
  
5.  Přidat **assemblyIdentity** jako podřízený element **dependentAssembly** elementu.  
  
6.  Přidejte následující atribut názvy a hodnoty, které mají **assemblyIdentity** element:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**Jméno**|**Microsoft.VisualStudio.Enterprise.ASPNetHelper**|  
    |**PublicKeyToken**|**b03f5f7f11d50a3a**|  
    |**Jazyková verze**|**Neutrální**|  
  
7.  Přidat **základu kódu** jako podřízený element **dependentAssembly** elementu.  
  
8.  Přidejte následující atribut názvy a hodnoty, které mají **základu kódu** element:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**Verze**|**10.0.0.0**|  
    |**href**|`PathToASPNetHelperDll`|  
  
     `PathToASPNetHelperDll` je adresa URL souboru Microsoft.VisualStudio.Enterprise.ASPNetHelper.dll. Pokud [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalována ve výchozím umístění, **href** hodnota by měla být `C:/Program%20Files/Microsoft%20Visual%20Studio%202010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL`  
  
```  
    <configuration>  
        <runtime>  
            <assemblyBinding   
                xmlns="urn:schemas-microsoft-com:asm.v1"  
            >  
                <dependentAssembly>  
                    <assemblyIdentity                         name="Microsoft.VisualStudio.Enterprise.ASPNetHelper"   
                        publicKeyToken="b03f5f7f11d50a3a"                         culture="neutral"   
                    />  
                    <codeBase   
                        version="10.0.0.0"  
                        href="file:///C:/Program%20Files/Microsoft%20Visual%20Studio%2010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL"   
                    />  
                </dependentAssembly>  
            </assemblyBinding>  
        </runtime>  
```  
  
### <a name="to-add-the-profiler-post-process-step-to-the-configurationsystemwebcompilation-element"></a>Chcete přidat krok po zpracování profileru do elementu configuration/system.web/compilation  
  
1.  V případě potřeby přidejte **system.web** prvku jako podřízeného prvku **konfigurace** element; jinak, přejděte k dalšímu kroku.  
  
     **System.web** element nemá žádné atributy. **Konfigurace** element může mít jen jeden **system.web** podřízený element.  
  
2.  V případě potřeby přidejte **kompilace** prvku jako podřízeného prvku **system.web** element; jinak, přejděte k dalšímu kroku.  
  
     **System.web** element může mít jen jeden **kompilace** podřízený element.  
  
3.  Odeberte všechny existující atributy z **kompilace** elementu a přidejte následující atribut název a hodnotu:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**assemblyPostProcessorType**|**Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter, Microsoft.VisualStudio.Enterprise.ASPNetHelper, verze = 10.0.0.0, Culture = neutral, PublicKeyToken = b03f5f7f11d50a3a**|  
  
```  
    <configuration>  
        <runtime>  
        . . .  
        </runtime>  
        <system.web>  
            <compilation  
                assemblyPostProcessorType="Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter,  
                    Microsoft.VisualStudio.Enterprise.ASPNetHelper,  
                    Version=10.0.0.0,  
                    Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"   
            />  
        </system.web>  
    <configuration>  
```  
  
### <a name="to-add-profiler-location-settings-to-the-configurationappsettings-element"></a>Chcete-li přidat nastavení umístění profileru do konfigurace/appSettings elementu  
  
1.  V případě potřeby přidejte **appSettings** prvku jako podřízeného prvku **konfigurace** element; jinak, přejděte k dalšímu kroku.  
  
     **AppSettings** element nemá žádné atributy. **Konfigurace** element může mít jen jeden **appSettings** podřízený element.  
  
2.  Přidat **přidat** jako podřízený element **appSettings** elementu.  
  
3.  Přidejte následující atribut názvy a hodnoty, které mají **přidat** element:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**Klíč**|**Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation**|  
    |**value**|`PerformanceToolsFolder` **\VSInstr.exe**|  
  
4.  Přidejte další **přidat** jako podřízený element **appSettings** elementu.  
  
5.  Přidejte následující atribut názvy a hodnoty k tomuto **přidat** element:  
  
    |Název atributu|Hodnota atributu|  
    |--------------------|---------------------|  
    |**Klíč**|**Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools**|  
    |**value**|`PerformanceToolsFolder`|  
  
     `PerformanceToolsFolder` je cesta profileru spustitelné soubory. Pokud [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] je nainstalována ve výchozím umístění, bude hodnota **10.0\Team C:\Program Files\Microsoft Visual Studio Tools nástroje**  
  
```  
    <configuration>  
        <runtime>  
        . . .  
        </runtime>  
        . . .  
        <system.web>  
        </system.web>  
        <appSettings>  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\vsinstr.exe"  
        />  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\"  
            />  
        </appSettings>  
    </configuration>  
```  
  
## <a name="example"></a>Příklad  
 Následující je soubor web.config dokončení, který umožňuje instrumentace a profilování z dynamicky kompilované [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] webové aplikace. Tento příklad předpokládá, že neexistují žádné další nastavení v souboru před úpravou.  
  
```  
<?xml version="1.0"?>  
    <configuration>  
        <runtime>  
            <assemblyBinding   
                xmlns="urn:schemas-microsoft-com:asm.v1"  
            >  
                <dependentAssembly>  
                    <assemblyIdentity   
                        name="Microsoft.VisualStudio.Enterprise.ASPNetHelper"   
                        publicKeyToken="b03f5f7f11d50a3a"  
                        culture="neutral"   
                    />  
                    <codeBase   
                        version="10.0.0.0"  
                        href="file:///C:/Program%20Files/Microsoft%20Visual%20Studio%2010.0/Common7/IDE/PrivateAssemblies/Microsoft.VisualStudio.Enterprise.ASPNetHelper.DLL"   
                    />  
                </dependentAssembly>  
            </assemblyBinding>  
        </runtime>  
        <system.web>  
            <compilation  
                assemblyPostProcessorType="Microsoft.VisualStudio.Enterprise.Common.AspPerformanceInstrumenter,  
                    Microsoft.VisualStudio.Enterprise.ASPNetHelper,  
                    Version=10.0.0.0,  
                    Culture=neutral,  
                    PublicKeyToken=b03f5f7f11d50a3a"   
            />  
        </system.web>  
        <appSettings>  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrLocation"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\vsinstr.exe"  
            />  
            <add  
                key="Microsoft.VisualStudio.Enterprise.AspNetHelper.VsInstrTools"  
                value="C:\Program Files\Microsoft Visual Studio 10.0\Team Tools\Performance Tools\"  
            />  
        </appSettings>  
    </configuration>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [Postupy: instrumentace dynamicky kompilované aplikace ASP.NET a shromažďování podrobných dat časování](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-app-and-collect-timing-data.md)   
 [Postupy: instrumentace dynamicky kompilované aplikace ASP.NET a shromažďování dat paměti](../profiling/how-to-instrument-a-dynamically-compiled-aspnet-web-application-and-collect-memory-data.md)