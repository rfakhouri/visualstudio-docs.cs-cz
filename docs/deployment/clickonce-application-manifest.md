---
title: ClickOnce – Manifest aplikace | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- application manifests [ClickOnce]
- ClickOnce, application manifests
ms.assetid: 29570cec-4e53-4660-a850-abc4fa150243
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 52d5a288444b1e98df75e6748fa31176b27211b0
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="clickonce-application-manifest"></a>ClickOnce – manifest aplikace 
A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace je soubor XML, který popisuje aplikaci, která se nasazuje pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty aplikací mít následující elementy a atributy.  
  
|Prvek|Popis|Atributy|  
|-------------|-----------------|----------------|  
|[\<sestavení > elementu](../deployment/assembly-element-clickonce-application.md)|Požadováno. Element nejvyšší úrovně.|`manifestVersion`|  
|[\<assemblyIdentity > elementu](../deployment/assemblyidentity-element-clickonce-application.md)|Požadováno. Určuje primární sestavení z [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[\<trustInfo > elementu](../deployment/trustinfo-element-clickonce-application.md)|Identifikuje požadavky na zabezpečení aplikace.|Žádné|  
|[\<entryPoint > elementu](../deployment/entrypoint-element-clickonce-application.md)|Požadováno. Identifikuje vstupní bod pro kód aplikace.|`name`|  
|[\<závislost > elementu](../deployment/dependency-element-clickonce-application.md)|Požadováno. Identifikuje každá závislost požadované pro spuštění aplikace. Volitelně identifikuje sestavení, které musí být předinstalována.|Žádné|  
|[\<Soubor > elementu](../deployment/file-element-clickonce-application.md)|Volitelné. Identifikuje každý soubor nonassembly, který se používá v aplikaci. Může obsahovat data izolace modelu COM (Component Object) přidružené k souboru.|`name`<br /><br /> `size`<br /><br /> `group`<br /><br /> `optional`<br /><br /> `writeableType`|  
|[\<fileAssociation > elementu](../deployment/fileassociation-element-clickonce-application.md)|Volitelné. Určuje příponu souboru, který se má přidružit aplikace.|`extension`<br /><br /> `description`<br /><br /> `progid`<br /><br /> `defaultIcon`|  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Souboru manifestu aplikace identifikuje aplikace nasazené pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Další informace o [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], najdete v části [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md).  
  
## <a name="file-location"></a>Umístění souboru  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace je specifická pro jednu verzi nasazení. Z tohoto důvodu mají být uloženy odděleně od manifesty nasazení. Běžné konvence je jejich umístění v podadresáři s názvem po přidružené verze.  
  
 Manifest aplikace musí být podepsané vždy před jejich nasazením. Pokud je ručně změnit manifest aplikace, musíte použít mage.exe znovu podepsání manifestu aplikace, manifest nasazení aktualizovat a pak se znovu přihlaste manifest nasazení. Další informace najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="file-name-syntax"></a>Syntaxe názvu souboru  
 Název [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] souboru manifestu aplikace by měl být úplný název a rozšíření aplikace, jako v identifikovat `assemblyIdentity` element, za nímž následuje manifest rozšíření. Manifest aplikace, která odkazuje na aplikaci Example.exe by například použít následující syntaxe názvu souboru.  
  
 `example.exe.manifest`  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje manifest aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd" manifestVersion="1.0" xmlns:asmv3="urn:schemas-microsoft-com:asm.v3" xmlns:dsig="http://www.w3.org/2000/09/xmldsig#" xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2" xmlns="urn:schemas-microsoft-com:asm.v2" xmlns:asmv1="urn:schemas-microsoft-com:asm.v1" xmlns:asmv2="urn:schemas-microsoft-com:asm.v2" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">  
  <asmv1:assemblyIdentity name="My Application Deployment.exe" version="1.0.0.0" publicKeyToken="43cb1e8e7a352766" language="neutral" processorArchitecture="x86" type="win32" />  
  <application />  
  <entryPoint>  
    <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
  <trustInfo>  
    <security>  
      <applicationRequestMinimum>  
        <PermissionSet Unrestricted="true" ID="Custom" SameSite="site" />  
        <defaultAssemblyRequest permissionSetReference="Custom" />  
      </applicationRequestMinimum>  
      <requestedPrivileges xmlns="urn:schemas-microsoft-com:asm.v3">  
        <!--  
          UAC Manifest Options  
          If you want to change the Windows User Account Control level replace the   
          requestedExecutionLevel node with one of the following.  
  
        <requestedExecutionLevel  level="asInvoker" uiAccess="false" />  
        <requestedExecutionLevel  level="requireAdministrator" uiAccess="false" />  
        <requestedExecutionLevel  level="highestAvailable" uiAccess="false" />  
  
         If you want to utilize File and Registry Virtualization for backward   
         compatibility then delete the requestedExecutionLevel node.  
    -->  
        <requestedExecutionLevel level="asInvoker" uiAccess="false" />  
      </requestedPrivileges>  
    </security>  
  </trustInfo>  
  <dependency>  
    <dependentOS>  
      <osVersionInfo>  
        <os majorVersion="4" minorVersion="10" buildNumber="0" servicePackMajor="0" />  
      </osVersionInfo>  
    </dependentOS>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
      <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="4.0.20506.0" />  
    </dependentAssembly>  
  </dependency>  
  <dependency>  
    <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="4096">  
      <assemblyIdentity name="MyApplication" version="1.0.0.0" language="neutral" processorArchitecture="x86" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAINCONTROLLER\UserMe" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
...  
</Signature></r:issuer></r:license></msrel:RelData></KeyInfo></Signature></asmv1:assembly>  
```  
  
## <a name="see-also"></a>Viz také  
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)