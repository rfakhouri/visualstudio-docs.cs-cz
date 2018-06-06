---
title: '&lt;závislost&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
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
- manifests [ClickOnce], dependency element
- <dependency> element [ClickOnce application manifest]
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fee364b7116bf69b961726ec2154809f66f9bc45
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815032"
---
# <a name="ltdependencygt-element-clickonce-application"></a>&lt;závislost&gt; – Element (ClickOnce aplikace)
Identifikuje závislostí platformu nebo sestavení, která je vyžadována pro aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
  
      <dependency>  
   <dependentOS  
      supportURL  
      description  
   >  
      <osVersionInfo>  
         <os  
            majorVersion  
            minorVersion  
            buildNumber  
            servicePackMajor  
            servicePackMinor  
            productType  
            suiteType  
         />   
      </osVersionInfo>  
   </dependentOS>  
   <dependentAssembly  
      dependencyType  
      allowDelayedBinding  
      group  
      codeBase  
      size  
   >  
      <assemblyIdentity  
         name  
         version  
         processorArchitecture  
         language  
      >  
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
  
      </assemblyIdentity>  
   </dependentAssembly>  
</dependency>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `dependency` Prvek je nutný. Může být několik instancí `dependency` ve stejném manifestu aplikace.  
  
 `dependency` Element nemá žádné atributy a obsahuje následující podřízené prvky.  
  
### <a name="dependentos"></a>dependentOS  
 Volitelné. Obsahuje `osVersionInfo` elementu. `dependentOS` a `dependentAssembly` elementy se vzájemně vylučují: jeden z nich musí existovat `dependency` elementu, ale ne obojí.  
  
 `dependentOS` podporuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`supportUrl`|Volitelné. Určuje adresu URL podpory pro závislé platformu. Tato adresa URL se zobrazí uživateli, pokud je nalezena požadovaná platforma.|  
|`description`|Volitelné. Popisuje, v podobě čitelný, operační systém, který je popsaný v `dependentOS` elementu.|  
  
### <a name="osversioninfo"></a>osVersionInfo  
 Požadováno. Tento element je podřízená `dependentOS` elementu a obsahuje `os` elementu. Tento element nemá žádné atributy.  
  
### <a name="os"></a>operační systém  
 Požadováno. Tento element je podřízená `osVersionInfo` elementu. Tento element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`majorVersion`|Požadováno. Určuje hlavní číslo verze operačního systému.|  
|`minorVersion`|Požadováno. Určuje číslo podverze operačního systému.|  
|`buildNumber`|Požadováno. Určuje číslo sestavení operačního systému.|  
|`servicePackMajor`|Požadováno. Určuje hlavní číslo aktualizace service pack operačního systému.|  
|`servicePackMinor`|Volitelné. Určuje dílčí číslo aktualizace service pack operačního systému.|  
|`productType`|Volitelné. Určuje hodnotu typu produktu. Platné hodnoty jsou `server`, `workstation`, a `domainController`. Například pro systém Windows 2000 Professional, je hodnota tohoto atributu `workstation`.|  
|`suiteType`|Volitelné. Identifikuje sady produktů, která je k dispozici v systému nebo typ konfigurace systému. Platné hodnoty jsou `backoffice`, `blade`, `datacenter`, `enterprise`, `home`, `professional`, `smallbusiness`, `smallbusinessRestricted`, a `terminal`. Například pro systém Windows 2000 Professional, je hodnota tohoto atributu `professional`.|  
  
### <a name="dependentassembly"></a>dependentAssembly –  
 Volitelné. Obsahuje `assemblyIdentity` elementu. `dependentOS` a `dependentAssembly` elementy se vzájemně vylučují: jeden z nich musí existovat `dependency` elementu, ale ne obojí.  
  
 `dependentAssembly` má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`dependencyType`|Požadováno. Určuje typ závislosti. Platné hodnoty jsou `preprequisite` a `install`. `install` Sestavení je nainstalován jako součást [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. A `prerequisite` sestavení musí existovat v globální mezipaměti sestavení (GAC) před [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] instalací aplikace.|  
|`allowDelayedBinding`|Požadováno. Určuje, zda lze načíst prostřednictvím kódu programu za běhu sestavení.|  
|`group`|Volitelné. Pokud `dependencyType` je atribut nastaven na `install`, označí pojmenovanou skupinu sestavení pouze instalaci na vyžádání. Další informace najdete v tématu [návod: stahování sestavení na vyžádání pomocí ClickOnce pomocí rozhraní API nasazení návrháře](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md).<br /><br /> Pokud nastavena na `framework` a `dependencyType` je atribut nastaven na `prerequisite`, označí sestavení v rámci rozhraní .NET Framework. Sestavení v globální mezipaměti (aktivit GAC) není zaškrtnuta možnost pro toto sestavení, při instalaci na [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] a novějších verzích.|  
|`codeBase`|Požadováno, pokud `dependencyType` je nastavena na hodnotu `install`. Cesta k závislého sestavení. Může být absolutní cestu nebo cestu k kódu manifestu základní. Tato cesta musí být platný identifikátor URI manifest sestavení, aby byla platná.|  
|`size`|Požadováno, pokud `dependencyType` je nastavena na hodnotu `install`. Velikost závislého sestavení v bajtech.|  
  
### <a name="assemblyidentity"></a>assemblyIdentity –  
 Požadováno. Tento element je podřízená `dependentAssembly` elementu a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Určuje název aplikace.|  
|`version`|Požadováno. Určuje číslo verze aplikace v následujícím formátu: `major.minor.build.revision`|  
|`publicKeyToken`|Volitelné. Určuje řetězec šestnáctkových 16 znaků, který představuje posledních 8 bajtů `SHA-1` hash hodnotu veřejný klíč, pod kterým je podepsaná aplikace nebo sestavení. Veřejný klíč používaný k podepisování katalogu musí být 2 048 bitů nebo více.|  
|`processorArchitecture`|Volitelné. Určuje procesor. Platné hodnoty jsou `x86` pro 32bitový systém Windows a `I64` pro 64bitový systém Windows.|  
|`language`|Volitelné. Určuje kódy jazyků dvě části, třeba cs-cz, sestavení.|  
  
### <a name="hash"></a>hash  
 `hash` Element je volitelným podřízeným `assemblyIdentity` elementu. `hash` Element nemá žádné atributy.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] používá algoritmické hodnotu hash všech souborů v aplikaci jako kontrolu zabezpečení, ujistěte se, že žádné soubory byly změněny po nasazení. Pokud `hash` element neuvedete, nebude provedena kontrola. Proto vynechání `hash` element se nedoporučuje.  
  
### <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` Je požadovaný podřízený element `hash` elementu. `dsig:Transforms` Element nemá žádné atributy.  
  
### <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` Je požadovaný podřízený element `dsig:Transforms` elementu. `dsig:Transform` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
### <a name="dsigdigestmethod"></a>dsig: DigestMethod  
 `dsig:DigestMethod` Je požadovaný podřízený element `hash` elementu. `dsig:DigestMethod` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
### <a name="dsigdigestvalue"></a>dsig: DigestValue  
 `dsig:DigestValue` Je požadovaný podřízený element `hash` elementu. `dsig:DigestValue` Element nemá žádné atributy. Jeho textová hodnota je vypočtená hodnota hash pro zadaný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Všechna sestavení, které používá vaše aplikace musí mít odpovídající `dependency` elementu. Závislá sestavení nezahrnují sestavení, které musí být předinstalován v globální mezipaměti sestavení jako sestavení platformy.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `dependency` elementů v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. Tento příklad kódu je součástí většího příkladu vztahujícího se pro [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md) tématu.  
  
```xml  
<dependency>  
  <dependentOS>  
    <osVersionInfo>  
      <os   
        majorVersion="4"   
        minorVersion="10"   
        buildNumber="0"   
        servicePackMajor="0" />  
    </osVersionInfo>  
  </dependentOS>  
</dependency>  
<dependency>  
  <dependentAssembly  
    dependencyType="preRequisite"  
    allowDelayedBinding="true">  
    <assemblyIdentity  
      name="Microsoft.Windows.CommonLanguageRuntime"  
      version="4.0.20506.0" />  
  </dependentAssembly>  
</dependency>  
  
<dependency>  
  <dependentAssembly  
    dependencyType="install"  
    allowDelayedBinding="true"  
    codebase="MyApplication.exe"  
    size="4096">  
    <assemblyIdentity  
      name="MyApplication"  
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <hash>  
      <dsig:Transforms>  
        <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
      </dsig:Transforms>  
      <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
      <dsig:DigestValue>DpTW7RzS9IeT/RBSLj54vfTEzNg=</dsig:DigestValue>  
    </hash>  
  </dependentAssembly>  
</dependency>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [\<závislost > elementu](../deployment/dependency-element-clickonce-deployment.md)