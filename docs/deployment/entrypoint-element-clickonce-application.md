---
title: '&lt;entryPoint&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#commandLine
- urn:schemas-microsoft-com:asm.v2#entryPoint
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <entryPoint> element [ClickOnce application manifest]
- manifests [ClickOnce], entryPoint element
ms.assetid: 10ad3083-10c1-4189-a870-9bba2eab244f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: beb140a64a415ab1a42f8157e2fafb1d20f9569a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31565247"
---
# <a name="ltentrypointgt-element-clickonce-application"></a>&lt;entryPoint&gt; – Element (ClickOnce aplikace)
Identifikuje sestavení, které by měla být spuštěna při to [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace běží na klientském počítači.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <entryPoint  
   name  
>  
   <assemblyIdentity  
      name  
      version  
      processorArchitecture  
      language  
   />  
   <commandLine  
      file  
      parameters  
   />  
   <customHostRequired />  
   <customUX />  
</entryPoint>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `entryPoint` Element je povinná a je v `urn:schemas-microsoft-com:asm.v2` oboru názvů. Může existovat pouze jedna `entryPoint` element definovaný v manifestu aplikace.  
  
 `entryPoint` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Volitelné. Tuto hodnotu nepoužívá rozhraní .NET Framework.|  
  
 `entryPoint` obsahuje následující prvky.  
  
## <a name="assemblyidentity"></a>assemblyIdentity –  
 Požadováno. Role `assemblyIdentity` a jeho atributy je definována v [ \<assemblyIdentity > Element](../deployment/assemblyidentity-element-clickonce-application.md).  
  
 `processorArchitecture` Atribut tohoto elementu a `processorArchitecture` definovaný v atributu `assemblyIdentity` jinde v aplikaci manifest se musí shodovat.  
  
## <a name="commandline"></a>příkazového řádku  
 Požadováno. Musí být podřízenou `entryPoint` elementu. Nemá žádné podřízené elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`file`|Požadováno. Místní odkaz na sestavení pro spuštění [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tato hodnota nemůže obsahovat lomítko (/) ani zpětné lomítko (\\) oddělovače cest.|  
|`parameters`|Požadováno. Popisuje akce, který má být provedena se vstupním bodem. Jediná platná hodnota je `run`; Pokud je zadán prázdný řetězec, `run` se předpokládá.|  
  
## <a name="customhostrequired"></a>customHostRequired  
 Volitelné. Pokud zahrnuty, určuje, že toto nasazení obsahuje součást, která bude nasazena uvnitř vlastního hostitele a není samostatné aplikace.  
  
 Pokud se nachází tento element `assemblyIdentity` a `commandLine` elementů nesmí být k dispozici také. Pokud ano, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dosáhne chyby ověření během instalace.  
  
 Tento element má žádné atributy a žádné podřízené objekty.  
  
## <a name="customux"></a>customUX  
 Volitelné. Určuje, že aplikace je nainstalovaná a udržuje vlastní instalační program a není vytvořit položku nabídky Start, zástupce nebo přidat nebo odebrat programy položku.  
  
```  
<customUX xmlns="urn:schemas-microsoft-com:clickonce.v1" />  
```  
  
 Aplikace, která obsahuje prvek customUX musí poskytnout vlastní instalační program, že používá <xref:System.Deployment.Application.InPlaceHostingManager> nainstalovat třída k provedení operace. Dvakrát klikněte na jeho zaváděcí manifest nebo setup.exe nemůže nainstalovat aplikace s tímto elementem. Vlastní instalační program můžete vytvořit položky nabídky Start, zástupce a položky Přidat nebo odebrat programy. Pokud vlastní instalační program nevytvoří položku Přidat nebo odebrat programy, musí uložit identifikátor odběru poskytované <xref:System.Deployment.Application.GetManifestCompletedEventArgs.SubscriptionIdentity%2A> vlastnost a povolit uživatelům odinstalovat aplikaci později voláním <xref:System.Deployment.Application.InPlaceHostingManager.UninstallCustomUXApplication%2A> metoda. Další informace najdete v tématu [návod: vytváření vlastní instalační program pro aplikaci ClickOnce](../deployment/walkthrough-creating-a-custom-installer-for-a-clickonce-application.md).  
  
## <a name="remarks"></a>Poznámky  
 Tento element identifikuje sestavení a vstupní bod pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
 Nemůžete použít `commandLine` předat parametry do své aplikace za běhu. Dostanete parametrů řetězce dotazu pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení z aplikace <xref:System.AppDomain>. Další informace najdete v tématu [postupy: načtení informací řetězce dotazu v Online aplikace ClickOnce](../deployment/how-to-retrieve-query-string-information-in-an-online-clickonce-application.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `entryPoint` element v manifestu aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tento příklad kódu je součástí většího příkladu vztahujícího se pro [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md) tématu.  
  
```  
<!-- Identify the main code entrypoint. -->  
<!-- This code runs the main method in an executable assembly. -->  
  <entryPoint>  
    <assemblyIdentity   
      name="MyApplication"   
      version="1.0.0.0"  
      language="neutral"  
      processorArchitecture="x86" />  
    <commandLine file="MyApplication.exe" parameters="" />  
  </entryPoint>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)