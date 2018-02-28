---
title: "Manifesty aplikací pro řešení Office | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 6bc73d9770c35ecc2f46d65c4ecd6977b587985d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="application-manifests-for-office-solutions"></a>Manifesty aplikace pro řešení Office
  Manifest aplikace je soubor XML, který popisuje sestavení, která jsou načtena do řešení Microsoft Office. Použít vývojových nástrojů Microsoft Office v sadě Visual Studio [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] aplikace manifestu schéma definované v [Manifest aplikace ClickOnce](/visualstudio/deployment/clickonce-application-manifest) odkaz.  
  
 Manifesty aplikace pro řešení Office použijte následující [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] elementů a atributů.  
  
|Prvek|Popis|Atributy|  
|-------------|-----------------|----------------|  
|[& č. 60; sestavení & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|Požadováno. Element nejvyšší úrovně.|`manifestVersion`|  
|[& č. 60; assemblyIdentity & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|Požadováno. Identifikuje [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] primární sestavení aplikace.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[& č. 60; trustInfo & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|Identifikuje požadavky na zabezpečení aplikace.|Žádné|  
|[& č. 60; entryPoint & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|Požadováno. Identifikuje vstupní bod aplikace kód pro spuštění.|`name`<br /><br /> `dependencyName`<br /><br /> `customHostSpecified`|  
|[& č. 60; závislosti & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|Požadováno. Identifikuje každá závislost požadované pro spuštění aplikace. Volitelně identifikuje sestavení, které musí být předinstalována.|Žádné|  
|[& č. 60; souboru & č. 62; Element &#40; Aplikace ClickOnce &#41;](/visualstudio/deployment/file-element-clickonce-application)|Požadováno. Identifikuje každého souboru bez sestavení, který se používá v aplikaci. Může obsahovat data izolace modelu COM (Component Object) přidružené k souboru.|`name`<br /><br /> `size`|  
  
 Manifesty aplikace pro řešení Office mají následující element `co.v1` oboru názvů.  
  
```  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 Tyto manifesty aplikací mít také následující elementů a atributů v `vstav3` oboru názvů.  
  
```  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|Prvek|Popis|Atributy|  
|-------------|-----------------|----------------|  
|[& č. 60; customhostspecified – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|Požadováno. Označí manifest konkrétně jako řešení Office.|Žádné|  
|[& č. 60; doplněk & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/addin-element-office-development-in-visual-studio.md)|Požadováno. Ukládá vstupní body do jednoho oboru názvů.|Žádné|  
|[& č. 60; entrypointscollection – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|Požadováno. Všechna sestavení pro řešení Office jeden nebo více skupin.|`id`|  
|[& č. 60; entryPoints & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|Požadováno. Skupiny všechna sestavení ke spuštění řešení Office.|Žádné|  
|[& č. 60; entryPoint & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|Požadováno. Identifikuje sestavení, ke spuštění v řešení Office.|`class`<br /><br /> `contract`|  
|[& č. 60; aktualizace & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/update-element-office-development-in-visual-studio.md)|Požadováno. Nakonfiguruje aktualizace pro řešení.|`enabled`<br /><br /> `expiration`|  
|[& č. 60; postactions – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|Volitelné. Skupiny všechny po nasazení akce, které se spustit po instalaci řešení pro systém Office.|Žádné|  
|[& č. 60; postAction & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|Volitelné. Identifikuje akce po nasazení.|Žádné|  
|[& č. 60; postactiondata – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|Volitelné. Konfiguruje data pro akci po nasazení.|Žádné|  
|[& č. 60; aplikace & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/application-element-office-development-in-visual-studio.md)|Požadováno. Zabalí informace specifické pro aplikaci do jednoho uzlu.|Žádné|  
|[& č. 60; přizpůsobení & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|Požadováno. Všechny informace specifické pro hostitele aplikace ukládá v samostatný obor názvů.|Žádné|  
|[& č. 60; přizpůsobení & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/customization-element-office-development-in-visual-studio.md)|Požadováno. Ukládá informace specifické pro hostitele aplikace v samostatný obor názvů.|`xmlns`|  
|[& č. 60; dokument & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/document-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro řešení na úrovni dokumentu. Ukládá informace specifické pro přizpůsobení.|`solutionId`|  
|[& č. 60; appAddin & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro řešení na úrovni aplikace. Ukládá informace specifické pro přizpůsobení.|`application`<br /><br /> `loadBehavior`<br /><br /> `keyName`|  
|[& č. 60; friendlyName & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|Volitelné. Ukládá název VSTO doplněk, který se zobrazí v seznamu nainstalovaných doplňků VSTO.|Žádné|  
|[& č. 60; Popis & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/description-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro doplňky VSTO. Ukládá popis, který se zobrazí v seznamu nainstalovaných programů.|Žádné|  
|[& č. 60; formregions – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.|Žádné|  
|[& č. 60; formRegion & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.|`Name`|  
|[& č. 60; vstoruntime – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|Požadováno. Popisuje určitou verzi sady Visual Studio Tools for Office runtime, který je podporuje řešení pro Office.|`release`<br /><br /> `version`<br /><br /> `supportUrl`|  
  
## <a name="remarks"></a>Poznámky  
 Aplikace můžete upravit ručně a manifesty nasazení v řešeních pro systém Office. Později musíte aplikaci znovu podepsat a manifesty nasazení pomocí generování manifestu a nástroj pro úpravy (mage.exe a mageui.exe). Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="file-location"></a>Umístění souboru  
 Manifest aplikace je specifická pro jednu verzi řešení. Z tohoto důvodu by měl být manifestů aplikace ukládají odděleně od manifesty nasazení. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Umístí soubory specifické pro verzi v podadresáři s názvem podle přidružené verze v **soubory aplikace** podadresář ve složce publikování.  
  
## <a name="file-name-syntax"></a>Syntaxe názvu souboru  
 Název souboru manifestu aplikace by měl být úplný název a příponu aplikace, jako v identifikovat `assemblyIdentity` element, za nímž následuje manifest rozšíření. Manifest aplikace, který odkazuje na přizpůsobení OutlookAddIn1.dll by například použít následující syntaxe názvu souboru.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>Viz také  
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  