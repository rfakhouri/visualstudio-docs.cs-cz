---
title: 'Postupy: použití ClickOnce k nasazení aplikace, které můžete spustit na více verzích rozhraní .NET Framework | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, multiple .NET Framework versions
- ClickOnce deployment, multiple .NET Framework versions
- deploying applications [ClickOnce], multiple .NET Framework versions
ms.assetid: e0a8c330-21bc-4eb2-b936-fd0f3c3221f1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: c05d1317c2b8040baf23c98cff8a032f14f47798
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-use-clickonce-to-deploy-applications-that-can-run-on-multiple-versions-of-the-net-framework"></a>Postupy: Použití ClickOnce k nasazení aplikací, jež lze provozovat na více verzích rozhraní .NET Framework
Můžete nasadit aplikaci, která se zaměřuje na více verzí rozhraní .NET Framework pomocí technologie ClickOnce nasazení. To vyžaduje generovat a aktualizovat manifestů aplikace a nasazení.  
  
> [!NOTE]
>  Než změníte aplikace pro cílení na více verzí rozhraní .NET Framework, měli byste zajistit, že je aplikace spuštěna s více verzemi rozhraní .NET Framework. Modul common language runtime verze se liší mezi [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] oproti rozhraní .NET Framework 2.0, .NET Framework 3.0 a rozhraní .NET Framework 3.5.  
  
 Tento proces vyžaduje následující kroky:  
  
1.  Generování manifestů aplikace a nasazení.  
  
2.  Manifest nasazení seznam několik verzí .NET Framework změňte.  
  
3.  Soubor app.config seznam kompatibilní verze runtime rozhraní .NET Framework změňte.  
  
4.  Manifest aplikace k označení závislé sestavení jako sestavení rozhraní .NET Framework změňte.  
  
5.  Podepsání manifestu aplikace.  
  
6.  Aktualizujte a podepsání manifestu nasazení.  
  
### <a name="to-generate-the-application-and-deployment-manifests"></a>Pro generování manifestů aplikace a nasazení  
  
-   Pomocí Průvodce publikování nebo publikování stránky v Návrháři projektu můžete publikovat aplikaci a generovat aplikace a soubory manifestu nasazení. Další informace najdete v tématu [postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md) nebo [publikovat stránku, Návrhář projektu](../ide/reference/publish-page-project-designer.md).  
  
### <a name="to-change-the-deployment-manifest-to-list-the-multiple-net-framework-versions"></a>Chcete-li změnit manifestu nasazení, aby obsahoval více verzí rozhraní .NET Framework  
  
1.  V adresáři pro publikování otevřete manifest nasazení pomocí editoru XML v sadě Visual Studio. Manifest nasazení má příponu názvu souboru .application.  
  
2.  Nahraďte kód XML mezi `<compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">` a `</compatibleFrameworks>` elementů pomocí XML, který uvádí podporované verze rozhraní .NET Framework pro vaši aplikaci.  
  
     Následující tabulka uvádí některé z dostupných verzí rozhraní .NET Framework a odpovídající soubor XML, který můžete přidat do manifestu nasazení.  
  
    |Verze rozhraní .NET Framework|XML|  
    |----------------------------|---------|  
    |4 klienta|\<Framework targetVersion = "4.0" profil = supportedRuntime – "Client" = "4.0.30319" / >|  
    |4 úplné|\<Framework targetVersion = "4.0" profil = "Úplná" supportedRuntime = "4.0.30319" / >|  
    |3.5 klienta|\<Framework targetVersion = "3.5" profil = supportedRuntime – "Client" = "2.0.50727" / >|  
    |3.5 úplné|\<Framework targetVersion = "3.5" profil = "Úplná" supportedRuntime = "2.0.50727" / >|  
    |3.0|\<Framework targetVersion = "3.0" supportedRuntime = "2.0.50727" / >|  
  
### <a name="to-change-the-appconfig-file-to-list-the-compatible-net-framework-runtime-versions"></a>Chcete-li změnit soubor app.config a seznam kompatibilní verze runtime rozhraní .NET Framework  
  
1.  V Průzkumníku řešení otevřete soubor App.config pomocí editoru XML v sadě Visual Studio.  
  
2.  Nahraďte (nebo přidejte) kód XML mezi `<startup>` a `</startup>` elementů pomocí XML, který uvádí podporované verze rozhraní .NET Framework pro vaši aplikaci.  
  
     Následující tabulka uvádí některé z dostupných verzí rozhraní .NET Framework a odpovídající soubor XML, který můžete přidat do manifestu nasazení.  
  
    |Verze runtime rozhraní .NET framework|XML|  
    |------------------------------------|---------|  
    |4 klienta|\<supportedRuntime – verze = "v4.0.30319" sku = ". NETFramework, verze = v4.0, profil klienta = "/ >|  
    |4 úplné|\<supportedRuntime – verze = "v4.0.30319" sku = ". NETFramework, verze = v4.0 "/ >|  
    |3.5 úplné|\<supportedRuntime version="v2.0.50727"/ >|  
    |3.5 klienta|\<supportedRuntime – verze = "v2.0.50727" sku = "Client" / >|  
  
### <a name="to-change-the-application-manifest-to-mark-dependent-assemblies-as-net-framework-assemblies"></a>Chcete-li změnit manifest aplikace k označení závislé sestavení jako sestavení rozhraní .NET Framework  
  
1.  V adresáři pro publikování otevřete manifest aplikace pomocí editoru XML v sadě Visual Studio. Manifest nasazení má příponu názvu souboru manifest.  
  
2.  Přidat `group="framework"` na XML závislosti pro ochranné sestavení (`System.Core`, `WindowsBase`, `Sentinel.v3.5Client`, a `System.Data.Entity`). Například soubor XML by měl vypadat asi takto:  
  
    ```  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" group="framework">  
    ```  
  
3.  Aktualizovat číslo verze `<assemblyIdentity>` element pro Microsoft.Windows.CommonLanguageRuntime číslo verze pro rozhraní .NET Framework, který je nejnižší společný jmenovatel. Například pokud aplikace cílí rozhraní .NET Framework 3.5 a [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)], použijte 2.0.50727.0 číslo verze a kódu XML by měl vypadat třeba takto:  
  
    ```  
    <dependency>  
      <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
        <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50727.0" />  
      </dependentAssembly>  
    </dependency>  
    ```  
  
### <a name="to-update-and-re-sign-the-application-and-deployment-manifests"></a>Pokud chcete aktualizovat a znovu podepsat aplikace a nasazení manifesty  
  
-   Aktualizujte a nové podepsání manifestů aplikace a nasazení. Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [\<compatibleFrameworks > elementu](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [\<závislost > elementu](../deployment/dependency-element-clickonce-application.md)   
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [Schéma konfiguračního souboru](/dotnet/framework/configure-apps/file-schema/index)