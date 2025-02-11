---
title: '&lt;závislost&gt; – Element (aplikace ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
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
- manifests [ClickOnce], dependency element
- <dependency> element [ClickOnce application manifest]
ms.assetid: 09d6a1e0-60f8-4fbd-843b-8e49ee3115a3
caps.latest.revision: 36
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: e79fadcab1a4f00c084d675c3267b5886772fe2c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199886"
---
# <a name="ltdependencygt-element-clickonce-application"></a>&lt;závislost&gt; – Element (aplikace ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Určuje závislost platformy nebo sestavení, která je požadována pro aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
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
 `dependency` Je vyžadován element. Může existovat více instancí `dependency` ve stejném manifestu aplikace.  
  
 `dependency` Prvek nemá žádné atributy a obsahuje následující podřízené prvky.  
  
### <a name="dependentos"></a>dependentOS  
 Volitelné. Obsahuje `osVersionInfo` elementu. `dependentOS` a `dependentAssembly` prvky se vzájemně vylučují: jeden z nich musí existovat `dependency` elementu, ale ne obojí.  
  
 `dependentOS` podporuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`supportUrl`|Volitelné. Určuje adresu URL podpory pro závislý platformu. Tato adresa URL zobrazí uživateli, pokud je nalezen aktuální platformě.|  
|`description`|Volitelné. Popisuje operační systém popsané v čitelné formě, `dependentOS` elementu.|  
  
### <a name="osversioninfo"></a>osVersionInfo  
 Povinný parametr. Tento element je podřízeným prvkem `dependentOS` elementu a obsahuje `os` elementu. Tento element nemá žádné atributy.  
  
### <a name="os"></a>operační systém  
 Povinný parametr. Tento element je podřízeným prvkem `osVersionInfo` elementu. Tento element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`majorVersion`|Povinný parametr. Určuje číslo hlavní verze operačního systému.|  
|`minorVersion`|Povinný parametr. Určuje číslo podverze operačního systému.|  
|`buildNumber`|Povinný parametr. Určuje číslo sestavení operačního systému.|  
|`servicePackMajor`|Povinný parametr. Určuje hlavní číslo aktualizace service pack operačního systému.|  
|`servicePackMinor`|Volitelné. Určuje dílčí číslo aktualizace service pack operačního systému.|  
|`productType`|Volitelné. Určuje hodnotu typu produktu. Platné hodnoty jsou `server`, `workstation`, a `domainController`. Například pro Windows 2000 Professional, je hodnota tohoto atributu `workstation`.|  
|`suiteType`|Volitelné. Identifikuje sadu produktů, která je k dispozici v systému nebo typ konfigurace systému. Platné hodnoty jsou `backoffice`, `blade`, `datacenter`, `enterprise`, `home`, `professional`, `smallbusiness`, `smallbusinessRestricted`, a `terminal`. Například pro Windows 2000 Professional, je hodnota tohoto atributu `professional`.|  
  
### <a name="dependentassembly"></a>dependentAssembly  
 Volitelné. Obsahuje `assemblyIdentity` elementu. `dependentOS` a `dependentAssembly` prvky se vzájemně vylučují: jeden z nich musí existovat `dependency` elementu, ale ne obojí.  
  
 `dependentAssembly` má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`dependencyType`|Povinný parametr. Určuje typ závislosti. Platné hodnoty jsou `preprequisite` a `install`. `install` Sestavení je nainstalován jako součást [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace. A `prerequisite` sestavení musí být k dispozici v globální mezipaměti sestavení (GAC) před [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci jde nainstalovat.|  
|`allowDelayedBinding`|Povinný parametr. Určuje, zda sestavení lze načíst prostřednictvím kódu programu za běhu.|  
|`group`|Volitelné. Pokud `dependencyType` atribut je nastaven na `install`, určuje skupinu s názvem sestavení tohoto nainstalují jenom na vyžádání. Další informace najdete v tématu [názorný postup: Stahování sestavení na vyžádání pomocí nasazení ClickOnce pomocí návrháře rozhraní API](../deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer.md).<br /><br /> Pokud nastavit `framework` a `dependencyType` atribut je nastaven na `prerequisite`, označí sestavení jako součást rozhraní .NET Framework. Pro toto sestavení nepovolenou mezipaměti globálního sestavení (GAC) při instalaci [!INCLUDE[net_v40_short](../includes/net-v40-short-md.md)] a novějších verzích.|  
|`codeBase`|Požadováno, pokud `dependencyType` atribut je nastaven na `install`. Cesta k závislého sestavení. Může být absolutní cesta nebo cesta relativní k kódu manifestu základní. Tato cesta musí být platný identifikátor URI platný v pořadí pro manifest sestavení.|  
|`size`|Požadováno, pokud `dependencyType` atribut je nastaven na `install`. Velikost závislého sestavení, v bajtech.|  
  
### <a name="assemblyidentity"></a>Vlastnost assemblyIdentity  
 Povinný parametr. Tento element je podřízeným prvkem `dependentAssembly` prvek a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Povinný parametr. Určuje název aplikace.|  
|`version`|Povinný parametr. Určuje číslo verze aplikace v následujícím formátu: `major.minor.build.revision`|  
|`publicKeyToken`|Volitelné. Určuje šestnáctkový řetězec 16 znacích představující posledních 8 bajtů `SHA-1` hash hodnoty veřejný klíč, pod kterým je podepsaná aplikace nebo sestavení. Veřejný klíč používaný k podepisování katalogu musí být 2 048 bitů nebo více.|  
|`processorArchitecture`|Volitelné. Určuje procesor. Platné hodnoty jsou `x86` pro 32bitová verze Windows a `I64` pro 64bitová verze Windows.|  
|`language`|Volitelné. Určuje jazyk kódy dvě části, třeba cs-cz, sestavení.|  
  
### <a name="hash"></a>hash  
 `hash` Je volitelný podřízený element `assemblyIdentity` elementu. `hash` Prvek nemá žádné atributy.  
  
 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] používá vylepšením hodnota hash všech souborů v aplikaci pro kontrolu zabezpečení, k zajištění, že žádné soubory byly změněny po nasazení. Pokud `hash` element není zahrnut, tato kontrola neproběhne. Proto vynechání `hash` element se nedoporučuje.  
  
### <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` Je požadovaný podřízený element `hash` elementu. `dsig:Transforms` Prvek nemá žádné atributy.  
  
### <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` Je požadovaný podřízený element `dsig:Transforms` elementu. `dsig:Transform` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus používaný k výpočtu algoritmu digest pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] je `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
### <a name="dsigdigestmethod"></a>dsig: DigestMethod  
 `dsig:DigestMethod` Je požadovaný podřízený element `hash` elementu. `dsig:DigestMethod` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus používaný k výpočtu algoritmu digest pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] je `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
### <a name="dsigdigestvalue"></a>dsig:DigestValue  
 `dsig:DigestValue` Je požadovaný podřízený element `hash` elementu. `dsig:DigestValue` Prvek nemá žádné atributy. Jeho textová hodnota je vypočítaný algoritmus hash pro zadaný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Všechna sestavení, které používá vaše aplikace musí mít odpovídající `dependency` elementu. Závislá sestavení neobsahují sestavení, která musí předinstalován v globální mezipaměti sestavení jako sestavení platformy.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `dependency` prvky [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifest aplikace. Tento příklad kódu je součástí většího příkladu určeného pro [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md) tématu.  
  
```  
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
 [Element \<dependency>](../deployment/dependency-element-clickonce-deployment.md)
