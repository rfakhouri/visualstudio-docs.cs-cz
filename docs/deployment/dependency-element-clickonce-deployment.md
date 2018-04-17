---
title: '&lt;závislost&gt; – Element (ClickOnce – nasazení) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#osVersionInfo
- urn:schemas-microsoft-com:asm.v2#os
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#dependency
- http://www.w3.org/2000/09/xmldsig#DigestValue
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
- urn:schemas-microsoft-com:asm.v2#dependentAssembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <dependency> element [ClickOnce deployment manifest]
ms.assetid: 9b4d2082-0347-4922-ac70-85f11b913039
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 8ffea3e279ba894f9990991ea620baaa50b3997d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltdependencygt-element-clickonce-deployment"></a>&lt;závislost&gt; – Element (ClickOnce – nasazení)
Určuje verzi aplikace k instalaci a umístění manifestu aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <dependency>   
   <dependentAssembly  
      preRequisite  
      visible  
      dependencyType  
      codeBase  
      size  
   >   
      <assemblyIdentity   
         name   
         version   
         publicKeyToken   
         processorArchitecture   
         language  
         type  
      />   
      <hash>  
         <dsig:Transforms>  
            <dsig:Transform  
                Algorithm  
            />  
         </dsig:Transforms>  
         <dsig:DigestMethod />  
         <dsig:DigestValue>  
         </dsig:DigestValue>  
      </hash>  
  
   </dependentAssembly>   
</dependency>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `dependency` Prvek je nutný. Nemá žádné atributy. Manifest nasazení může mít více `dependency` elementy.  
  
 `dependency` Element obvykle vyjadřuje závislosti pro hlavní aplikaci na sestavení, které jsou obsažené v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Pokud vaše aplikace Main.exe spotřebovává sestavení nazvané DotNetAssembly.dll, musí být toto sestavení uvedené v oddílu závislosti. Závislost, ale můžete také express jiné typy závislosti, jako je například závislosti na konkrétní verzi modulu CLR, sestavení v globální mezipaměti sestavení (GAC) nebo na objekt COM. Protože je technologie nasazení bezdotykový [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nelze inicializovat stažení a instalaci těchto typů závislosti, ale nemá zabránit spuštění aplikace Pokud jeden nebo více zadaných závislostí neexistují.  
  
## <a name="dependentassembly"></a>dependentAssembly –  
 Požadováno. Tento prvek obsahuje `assemblyIdentity` elementu. V následující tabulce jsou uvedeny atributy `dependentAssembly` podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`preRequisite`|Volitelné. Určuje, že toto sestavení by již měla existovat v mezipaměti GAC. Platné hodnoty jsou `true` a `false`. Pokud `true`a zadané sestavení neexistuje v mezipaměti GAC, aplikace se nepodaří spustit.|  
|`visible`|Volitelné. Identifikuje identitu nejvyšší úrovně aplikací, včetně jeho závislé součásti. Interně používán [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] ke správě úložiště a aktivace aplikace.|  
|`dependencyType`|Požadováno. Vztah mezi tuto závislost a aplikace. Platné hodnoty jsou:<br /><br /> -   `install`. Součást představuje samostatnou instalaci z aktuální aplikace.<br />-   `preRequisite`. Součást je požadován aktuální aplikace.|  
|`codebase`|Volitelné. Úplná cesta k manifestu aplikace.|  
|`size`|Volitelné. Velikost manifest aplikace v bajtech.|  
  
## <a name="assemblyidentity"></a>assemblyIdentity –  
 Požadováno. Tento element je podřízená `dependentAssembly` elementu. Obsah `assemblyIdentity` musí být stejný jak je popsáno v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. V následující tabulce jsou uvedeny atributy `assemblyIdentity` elementu.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Určuje název aplikace.|  
|`Version`|Požadováno. Určuje číslo verze aplikace, v následujícím formátu: `major.minor.build.revision`|  
|`publicKeyToken`|Požadováno. Určuje řetězec šestnáctkových 16 znaků, který představuje posledních 8 bajtů hodnotu hash SHA-1 veřejný klíč, pod kterým je podepsaná aplikace nebo sestavení. Veřejný klíč používaný k podepisování musí být 2048 bitů nebo vyšší.|  
|`processorArchitecture`|Požadováno. Určuje procesor. Platné hodnoty jsou `x86` pro 32bitový systém Windows a `IA64` pro 64bitový systém Windows.|  
|`Language`|Volitelné. Identifikuje dvě součásti kódu jazyka sestavení. Například EN-US, což je zkratka pro angličtinu (US). Výchozí hodnota je `neutral`. Tento element má `asmv2` oboru názvů.|  
|`type`|Volitelné. Pro zpětnou kompatibilitu s Windows-souběžného nainstalovat technologii. Pouze povolená hodnota je `win32`.|  
  
## <a name="hash"></a>hash  
 `hash` Element je volitelným podřízeným `file` elementu. `hash` Element nemá žádné atributy.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] Ujistěte se, že žádné soubory byly změněny po nasazení používá algoritmické hodnotu hash všech souborů v aplikaci jako kontrolu zabezpečení. Pokud `hash` element neuvedete, nebude provedena kontrola. Proto vynechání `hash` element se nedoporučuje.  
  
## <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` Je požadovaný podřízený element `hash` elementu. `dsig:Transforms` Element nemá žádné atributy.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` Je požadovaný podřízený element `dsig:Transforms` elementu. V následující tabulce jsou uvedeny atributy `dsig:Transform` elementu.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
## <a name="dsigdigestmethod"></a>dsig: DigestMethod  
 `dsig:DigestMethod` Je požadovaný podřízený element `hash` elementu. V následující tabulce jsou uvedeny atributy `dsig:DigestMethod` elementu.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
## <a name="dsigdigestvalue"></a>dsig: DigestValue  
 `dsig:DigestValue` Je požadovaný podřízený element `hash` elementu. `dsig:DigestValue` Element nemá žádné atributy. Jeho textová hodnota je vypočtená hodnota hash pro zadaný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Manifesty nasazení mají obvykle jeden `assemblyIdentity` element, který identifikuje název a verze manifestu aplikace.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `dependency` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení.  
  
```  
<!-- Identify the assembly dependencies -->  
<dependency>  
  <dependentAssembly dependencyType="install" allowDelayedBinding="true" codebase="MyApplication.exe" size="16384">  
    <assemblyIdentity name="MyApplication" version="0.0.0.0" cultural="neutral" processorArchitecture="msil" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
       <dsig:DigestValue>YzXYZJAvj9pgAG3y8jXUjC7AtHg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu určuje závislost na sestavení již nainstalována v mezipaměti GAC.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="GACAssembly" version="1.0.0.0" language="neutral" processorArchitecture="msil" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu určuje závislost na konkrétní verzi modulu CLR.  
  
```  
<dependency>  
  <dependentAssembly dependencyType="preRequisite" allowDelayedBinding="true">  
    <assemblyIdentity name="Microsoft.Windows.CommonLanguageRuntime" version="2.0.50215.0" />  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu určuje závislost operačního systému.  
  
```  
<dependency>  
   <dependentOS supportUrl="http://www.microsoft.com" description="Microsoft Windows Operating System">  
      <osVersionInfo>  
         <os majorVersion="4" minorVersion="10" />  
      </osVersionInfo>  
   </dependentOS>  
</dependency>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [\<závislost > elementu](../deployment/dependency-element-clickonce-application.md)