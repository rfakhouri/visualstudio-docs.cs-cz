---
title: 'Postupy: Zadejte adresu URL podpory pro jednotlivé předpoklady v nasazení ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, prerequisites
- ClickOnce deployment, URLs
ms.assetid: 590742c3-a286-4160-aa75-7a441bb2207b
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 86d4b765dc5e6c56fdc8e7a3b082afaa72accf49
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-specify-a-support-url-for-individual-prerequisites-in-a-clickonce-deployment"></a>Postupy: Určení adresy URL webu s podporou pro jednotlivé předpoklady v nasazení ClickOnce
A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] pro počet požadavků, které musí být k dispozici v klientském počítači pro můžete otestovat nasazení [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] spuštění aplikace. Patří mezi ně požadovaná minimální verze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], verzi operačního systému a všechny sestavení, které musí být předinstalován v globální mezipaměti sestavení (GAC). [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], ale nemůže nainstalovat některý z těchto předpokladů; Pokud není nalezen předpokladem, jednoduše zastaví instalaci a zobrazí se dialogové okno s vysvětlením, proč instalace se nezdařila.  
  
 Existují dvě metody pro instalaci požadovaných součástí. Můžete je pomocí aplikace zaváděcího nástroje nainstalovat. Alternativně můžete zadat adresu URL podpory pro jednotlivé předpoklady, které se zobrazí uživatelům na dialogové okno, pokud není nalezena předpokladů. Stránka odkazovaná touto adresou URL může obsahovat odkazy na pokyny k instalaci požadované součásti. Pokud aplikace nemá, zadejte adresu URL podpory pro jednotlivé předpoklady, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] zobrazí podporu adresa URL zadaná v manifestu nasazení pro aplikaci jako celek, pokud je definována.  
  
 Při [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], Mage.exe a MageUI.exe všechny slouží ke generování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, žádný z těchto nástrojů přímo nepodporuje určení adresu URL podpory pro jednotlivé předpoklady. Tento dokument popisuje, jak upravit vaše nasazení podporuje manifest aplikace a manifest nasazení zahrnout tyto adresy URL.  
  
### <a name="specifying-a-support-url-for-an-individual-prerequisite"></a>Zadat adresu URL podpory pro jednotlivé předpoklady  
  
1.  Otevřete manifest aplikace (soubor manifest) pro vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace v textovém editoru.  
  
2.  Požadavek k provedení operačního systému, přidejte `supportUrl` atribut `dependentOS` element:  
  
    ```  
     <dependency>  
        <dependentOS supportUrl="http://www.adatum.com/MyApplication/wrongOSFound.htm">  
          <osVersionInfo>  
            <os majorVersion="5" minorVersion="1" buildNumber="2600" servicePackMajor="0" servicePackMinor="0" />  
          </osVersionInfo>  
        </dependentOS>  
      </dependency>  
    ```  
  
3.  Předpokladem pro verzi modulu CLR, přidejte `supportUrl` atribut `dependentAssembly` položku, která určuje běžné závislostí modulu runtime jazyka:  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/wrongClrVersionFound.htm">  
          <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.30319.0" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
4.  Předpokladem pro sestavení, které musí být předinstalován v globální mezipaměti sestavení, nastavte `supportUrl` pro `dependentAssembly` element, který určuje požadované sestavení:  
  
    ```  
      <dependency>  
        <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true" supportUrl=" http://www.adatum.com/MyApplication/missingSampleGACAssembly.htm">  
          <assemblyIdentity name="SampleGACAssembly" version="5.0.0.0" publicKeyToken="04529dfb5da245c5" processorArchitecture="msil" language="neutral" />  
        </dependentAssembly>  
      </dependency>  
    ```  
  
5.  Volitelné. Pro aplikace, které cílí na rozhraní .NET Framework 4, otevřete manifest nasazení (soubor .application) pro vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace v textovém editoru.  
  
6.  Součásti rozhraní .NET Framework 4, přidejte `supportUrl` atribut `compatibleFrameworks` element:  
  
    ```  
    <compatibleFrameworks  xmlns="urn:schemas-microsoft-com:clickonce.v2" supportUrl="http://adatum.com/MyApplication/CompatibleFrameworks.htm">  
      <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.30319" />  
      <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.30319" />  
    </compatibleFrameworks>  
    ```  
  
7.  Jakmile jste ručně změnili manifest aplikace, musíte znovu podepsat manifest aplikace pomocí digitálního certifikátu, a aktualizovat a znovu podepsat manifest nasazení. Je nutné použít Mage.exe nebo MageUI.exe SDK nástroje k provedení této úlohy, jako obnovení těchto souborů pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vymaže ručně provedené změny. Další informace o používání Mage.exe k opětovné podepisování manifestů najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Adresu URL podpory se nezobrazí v dialogovém okně, pokud aplikace je označen ke spuštění v částečné důvěryhodnosti.  
  
## <a name="see-also"></a>Viz také  
 [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)   
 [\<compatibleFrameworks > elementu](../deployment/compatibleframeworks-element-clickonce-deployment.md)   
 [ClickOnce a kód Authenticode](../deployment/clickonce-and-authenticode.md)   
 [Nezbytné součásti nasazení aplikace](../deployment/application-deployment-prerequisites.md)