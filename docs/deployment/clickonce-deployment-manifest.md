---
title: ClickOnce – Manifest nasazení | Microsoft Docs
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
- ClickOnce, deployment manifests
- deployment manifests [ClickOnce]
ms.assetid: 8457e615-e3b6-4990-8dcf-11bc590e4e9b
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 5664c3505c44cb519365e7f15344d390eeebac0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="clickonce-deployment-manifest"></a>ClickOnce – manifest nasazení
Manifest nasazení je soubor XML, který popisuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení, včetně identifikace aktuální [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] verze aplikace pro nasazení.  
  
 Manifesty nasazení mají následující elementy a atributy.  
  
|Prvek|Popis|Atributy|  
|-------------|-----------------|----------------|  
|[\<sestavení > elementu](../deployment/assembly-element-clickonce-deployment.md)|Požadováno. Element nejvyšší úrovně.|`manifestVersion`|  
|[\<assemblyIdentity > elementu](../deployment/assemblyidentity-element-clickonce-deployment.md)|Požadováno. Identifikuje manifest aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `culture`|  
|[\<Popis > elementu](../deployment/description-element-clickonce-deployment.md)|Požadováno. Identifikuje informace o aplikaci použít k vytvoření přítomnosti prostředí a **přidat nebo odebrat programy** položky v Ovládacích panelech.|`publisher`<br /><br /> `product`<br /><br /> `supportUrl`|  
|[\<nasazení > elementu](../deployment/deployment-element-clickonce-deployment.md)|Volitelné. Identifikuje atributy použité pro nasazení aktualizací a vystavení systému.|`install`<br /><br /> `minimumRequiredVersion`<br /><br /> `mapFileExtensions`<br /><br /> `disallowUrlActivation`<br /><br /> `trustUrlParameters`|  
|[\<compatibleFrameworks > elementu](../deployment/compatibleframeworks-element-clickonce-deployment.md)|Požadováno. Určuje verzi rozhraní .NET Framework, kde můžete tuto aplikaci nainstalovat a spustit.|`SupportUrl`|  
|[\<závislost > elementu](../deployment/dependency-element-clickonce-deployment.md)|Požadováno. Určuje verzi aplikace k instalaci pro nasazení a umístění manifestu aplikace.|`preRequisite`<br /><br /> `visible`<br /><br /> `dependencyType`<br /><br /> `codebase`<br /><br /> `size`|  
|[\<publisherIdentity > elementu](../deployment/publisheridentity-element-clickonce-deployment.md)|Vyžaduje se pro podepsané manifesty. Obsahuje informace o vydavateli, který podepsal tento – manifest nasazení.|`Name`<br /><br /> `issuerKeyHash`|  
|[\<Podpis > elementu](../deployment/signature-element-clickonce-deployment.md)|Volitelné. Obsahuje informace potřebné k digitálnímu podepisování tento – manifest nasazení.|Žádné|  
|[\<customErrorReporting > elementu](../deployment/customerrorreporting-element-clickonce-deployment.md)|Volitelné. Určuje identifikátor URI zobrazíte, když dojde k chybě.|identifikátor URI|  
  
## <a name="remarks"></a>Poznámky  
 Soubor manifestu nasazení identifikuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace, včetně aktuální verze a dalších nastavení nasazení. Odkazuje na manifest aplikace, která popisuje aktuální verzi aplikace a všechny soubory obsažené v nasazení.  
  
 Další informace najdete v tématu [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md).  
  
## <a name="file-location"></a>Umístění souboru  
 Soubor manifestu nasazení odkazuje na správný manifest aplikace pro aktuální verzi aplikace. Pokud provedete novou verzi nasazení aplikace k dispozici, je nutné aktualizovat manifest nasazení odkazovat na nové manifest aplikace.  
  
 Soubor manifestu nasazení musí mít silné názvy a může také obsahovat certifikáty pro ověření vydavatele.  
  
## <a name="file-name-syntax"></a>Syntaxe názvu souboru  
 Název souboru manifestu nasazení musí končit příponou .application.  
  
## <a name="examples"></a>Příklady  
 Následující příklad kódu ukazuje manifest nasazení.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <assemblyIdentity   
    name="My Application Deployment.app"  
    version="1.0.0.0"  
    publicKeyToken="43cb1e8e7a352766"  
    language="neutral"  
    processorArchitecture="x86"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <description  
    asmv2:publisher="My Company Name"  
    asmv2:product="My Application"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <deployment install="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="0" unit="days" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="\\myServer\sampleDeployment\MyApplicationDeployment.application" />  
  </deployment>  
  <compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
    <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.20506" />  
    <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.20506" />  
  </compatibleFrameworks>  
  <dependency>  
    <dependentAssembly  
      dependencyType="install"  
      codebase="1.0.0.0\My Application Deployment.exe.manifest"  
      size="6756">  
      <assemblyIdentity  
        name="My Application Deployment.exe"  
        version="1.0.0.0"  
        publicKeyToken="43cb1e8e7a352766"  
        language="neutral"  
        processorArchitecture="x86"  
        type="win32" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>E506x9FwNauks7UjQywmzgtd3FE=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAIN\MyUsername" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
...  
</Signature></asmv1:assembly>  
```  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)