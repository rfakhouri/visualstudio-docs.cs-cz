---
title: "&lt;nasazení&gt; – Element (ClickOnce – nasazení) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#subscription
- urn:schemas-microsoft-com:asm.v2#beforeApplicationStartup
- urn:schemas-microsoft-com:asm.v2#deploymentProvider
- urn:schemas-microsoft-com:asm.v2#update
- urn:schemas-microsoft-com:asm.v2#deployment
- urn:schemas-microsoft-com:asm.v2#expiration
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <deployment> element [ClickOnce deployment manifest]
ms.assetid: 4fafa9c2-97a0-4cea-b8fd-9746dca33af4
caps.latest.revision: "30"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 0caff13f84208152b3fa2ff4e56a7a2c7f0b6dd7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltdeploymentgt-element-clickonce-deployment"></a>&lt;nasazení&gt; – Element (ClickOnce – nasazení)
Identifikuje atributy použité pro nasazení aktualizací a vystavení systému.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <deployment   
   install  
   minimumRequiredVersion  
   mapFileExtensions  
   disallowUrlActivation  
   trustUrlParameters  
>   
   <subscription>   
         <update>   
            <beforeApplicationStartup/>   
            <expiration  
               maximumAge  
               unit  
            />  
         </update>    
   </subscription>   
   <deploymentProvider   
      codebase   
   />   
</deployment>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `deployment` Element je povinná a je v `urn:schemas-microsoft-com:asm.v1` oboru názvů. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`install`|Požadováno. Určuje, zda tato aplikace definuje přítomnost na Windows **spustit** nabídky a v Ovládacích panelech **přidat nebo odebrat programy** aplikace. Platné hodnoty jsou `true` a `false`. Pokud `false`, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nejnovější verzi této aplikace bude vždy spouštět ze sítě a nerozpozná `subscription` elementu.|  
|`minimumRequiredVersion`|Volitelné. Určuje minimální verzi této aplikace, které můžete spustit na straně klienta. Pokud je číslo verze aplikace je menší než číslo verze zadané v manifestu nasazení, aplikace se nespustí. Čísla verzí je třeba zadat ve formátu `N.N.N.N`, kde `N` je celé číslo bez znaménka. Pokud `install` atribut je `false`, `minimumRequiredVersion` nesmí být nastavený.|  
|`mapFileExtensions`|Volitelné. Použije se výchozí hodnota `false`. Pokud `true`, všechny soubory v nasazení musí mít příponu .deploy. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Toto rozšíření mimo tyto soubory budou pruhu, jakmile je stáhne z webového serveru. Pokud je publikovat aplikace pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], automaticky přidá toto rozšíření pro všechny soubory. Tento parametr umožňuje všechny soubory v rámci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení ke stažení z webového serveru, které blokuje přenos souborů, které končí na "nebezpečnými" příponami .exe.|  
|`disallowUrlActivation`|Volitelné. Použije se výchozí hodnota `false`. Pokud `true`, zabraňuje aplikace nainstalované z spuštění kliknutím na adresu URL nebo zadáním adresy URL do aplikace Internet Explorer. Pokud `install` atribut není k dispozici, tento atribut je ignorován.|  
|`trustURLParameters`|Volitelné. Použije se výchozí hodnota `false`. Pokud `true`umožňuje adresu URL tak, aby obsahovala parametrů řetězce dotazu, které se předávají do aplikace, mnoho like argumenty příkazového řádku jsou předány aplikace příkazového řádku. Další informace najdete v tématu [postupy: načtení informací řetězce dotazu v Online aplikace ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).<br /><br /> Pokud `disallowUrlActivation` atribut je `true`, `trustUrlParameters` musí být vyloučeny z manifestu, nebo explicitně nastavit na `false`.|  
  
 `deployment` Element taky obsahuje následující podřízené prvky.  
  
## <a name="subscription"></a>Předplatné  
 Volitelné. Obsahuje `update` elementu. `subscription` Element nemá žádné atributy. Pokud `subscription` element neexistuje, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nebude nikdy kontrolovat aktualizace. Pokud `install` atribut `deployment` element je `false`, `subscription` element je ignorován, protože [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, který se spustí ze sítě, vždy používá nejnovější verze.  
  
## <a name="update"></a>Aktualizace  
 Požadováno. Tento element je podřízená `subscription` elementu a obsahuje buď `beforeApplicationStartup` nebo `expiration` elementu. `beforeApplicationStartup`a `expiration` nemůže být zároveň zadaná ve stejném manifestu nasazení.  
  
 `update` Element nemá žádné atributy.  
  
## <a name="beforeapplicationstartup"></a>beforeApplicationStartup  
 Volitelné. Tento element je podřízená `update` elementu a nemá žádné atributy. Když `beforeApplicationStartup` existuje element, aplikace bude blokované při [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vyhledávat aktualizace, pokud je klient online. Pokud tento element neexistuje, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nejprve vyhledá aktualizace podle hodnoty zadané pro `expiration` elementu. `beforeApplicationStartup`a `expiration` nemůže být zároveň zadaná ve stejném manifestu nasazení.  
  
## <a name="expiration"></a>vypršení platnosti  
 Volitelné. Tento element je podřízená `update` elementu, a nemá žádné podřízené objekty. `beforeApplicationStartup`a `expiration` nemůže být zároveň zadaná ve stejném manifestu nasazení. Když dojde k kontrolu aktualizací a je zjištěn aktualizovanou verzi, nové verze ukládá do mezipaměti průběhu existující verzi. Při příštím spuštění systému pak instalaci nové verze [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
 `expiration` Element podporuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`maximumAge`|Požadováno. Určuje, kolik aktuální aktualizaci měl být před aplikace provede kontrolu aktualizace. Jednotka času je dáno `unit` atribut.|  
|`unit`|Požadováno. Identifikuje jednotka času pro `maximumAge`. Platné jednotky jsou `hours`, `days`, a `weeks`.|  
  
## <a name="deploymentprovider"></a>deploymentProvider –  
 Pro rozhraní .NET Framework 2.0, tento prvek je nutný, pokud obsahuje manifest nasazení `subscription` části. Pro rozhraní .NET Framework 3.5 a novější Tento element je volitelný a použije výchozí server a cestu souboru, ve kterém byla zjištěna manifest nasazení.  
  
 Tento element je podřízená `deployment` elementu a má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`codebase`|Požadováno. Určuje umístění, jako identifikátor URI (Uniform Resource), manifest nasazení, který se používá k aktualizaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tento element také umožňuje předávání umístění aktualizace pro instalace z disku CD-ROM. Musí být platný identifikátor URI.|  
  
## <a name="remarks"></a>Poznámky  
 Můžete nakonfigurovat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikaci aktualizací na spuštění vyhledávání aktualizací po spuštění nebo nikdy nevyhledávat aktualizace. Postup kontroly aktualizací při spuštění, ujistěte se, že `beforeApplicationStartup` prvek existuje v `update` element. Po spuštění vyhledávání aktualizací, ujistěte se, že `expiration` prvek existuje v `update` elementu a že jsou poskytovány intervaly aktualizace.  
  
 Chcete-li zakázat zjišťování aktualizací, odeberte `subscription` elementu. Když zadáte v manifestu nasazení nikdy vyhledávání aktualizací, abyste mohli stále ručně zkontrolovat aktualizace pomocí <xref:System.Deployment.Application.ApplicationDeployment.CheckForUpdate%2A> metoda.  
  
 Další informace o tom, jak se deploymentProvider týká aktualizace, najdete v části [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
## <a name="examples"></a>Příklady  
 Následující příklad kódu ukazuje `deployment` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. V příkladu se používá `deploymentProvider` element k označení umístění upřednostňované aktualizace.  
  
```  
<deployment install="true" minimumRequiredVersion="2.0.0.0" mapFileExtension="true" trustUrlParameters="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="6" unit="hours" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="http://www.adatum.com/MyApplication.application" />  
  </deployment>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)