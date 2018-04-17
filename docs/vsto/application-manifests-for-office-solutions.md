---
title: Manifesty aplikací pro řešení Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0fa1ee09b3218fbcb485d7c3cd23e23ec18f463c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="application-manifests-for-office-solutions"></a>Manifesty aplikace pro řešení Office
  Manifest aplikace je soubor XML, který popisuje sestavení, která jsou načtena do řešení Microsoft Office. Použít vývojových nástrojů Microsoft Office v sadě Visual Studio [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] aplikace manifestu schéma definované v [Manifest aplikace ClickOnce](/visualstudio/deployment/clickonce-application-manifest) odkaz.  
  
 Manifesty aplikace pro řešení Office použijte následující [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] elementů a atributů.  
  
|Prvek|Popis|Atributy|  
|-------------|-----------------|----------------|  
|[&#60;sestavení&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|Požadováno. Element nejvyšší úrovně.|`manifestVersion`|  
|[&#60;assemblyIdentity&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|Požadováno. Identifikuje [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] primární sestavení aplikace.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `language`|  
|[&#60;trustInfo&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|Identifikuje požadavky na zabezpečení aplikace.|Žádné|  
|[&#60;entryPoint&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|Požadováno. Identifikuje vstupní bod aplikace kód pro spuštění.|`name`<br /><br /> `dependencyName`<br /><br /> `customHostSpecified`|  
|[&#60;závislost&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|Požadováno. Identifikuje každá závislost požadované pro spuštění aplikace. Volitelně identifikuje sestavení, které musí být předinstalována.|Žádné|  
|[&#60;soubor&#62; Element &#40;aplikace ClickOnce&#41;](/visualstudio/deployment/file-element-clickonce-application)|Požadováno. Identifikuje každého souboru bez sestavení, který se používá v aplikaci. Může obsahovat data izolace modelu COM (Component Object) přidružené k souboru.|`name`<br /><br /> `size`|  
  
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
|[&#60;customhostspecified –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|Požadováno. Označí manifest konkrétně jako řešení Office.|Žádné|  
|[&#60;doplněk&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/addin-element-office-development-in-visual-studio.md)|Požadováno. Ukládá vstupní body do jednoho oboru názvů.|Žádné|  
|[&#60;entrypointscollection –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|Požadováno. Všechna sestavení pro řešení Office jeden nebo více skupin.|`id`|  
|[&#60;entryPoints&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|Požadováno. Skupiny všechna sestavení ke spuštění řešení Office.|Žádné|  
|[&#60;entryPoint&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|Požadováno. Identifikuje sestavení, ke spuštění v řešení Office.|`class`<br /><br /> `contract`|  
|[&#60;Aktualizovat&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/update-element-office-development-in-visual-studio.md)|Požadováno. Nakonfiguruje aktualizace pro řešení.|`enabled`<br /><br /> `expiration`|  
|[&#60;postactions –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|Volitelné. Skupiny všechny po nasazení akce, které se spustit po instalaci řešení pro systém Office.|Žádné|  
|[&#60;postAction&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|Volitelné. Identifikuje akce po nasazení.|Žádné|  
|[&#60;postactiondata –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|Volitelné. Konfiguruje data pro akci po nasazení.|Žádné|  
|[&#60;aplikace&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/application-element-office-development-in-visual-studio.md)|Požadováno. Zabalí informace specifické pro aplikaci do jednoho uzlu.|Žádné|  
|[&#60;přizpůsobení&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|Požadováno. Všechny informace specifické pro hostitele aplikace ukládá v samostatný obor názvů.|Žádné|  
|[&#60;přizpůsobení&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/customization-element-office-development-in-visual-studio.md)|Požadováno. Ukládá informace specifické pro hostitele aplikace v samostatný obor názvů.|`xmlns`|  
|[&#60;dokument&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/document-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro řešení na úrovni dokumentu. Ukládá informace specifické pro přizpůsobení.|`solutionId`|  
|[&#60;appAddin&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro řešení na úrovni aplikace. Ukládá informace specifické pro přizpůsobení.|`application`<br /><br /> `loadBehavior`<br /><br /> `keyName`|  
|[&#60;friendlyName&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|Volitelné. Ukládá název VSTO doplněk, který se zobrazí v seznamu nainstalovaných doplňků VSTO.|Žádné|  
|[&#60;Popis&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/description-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro doplňky VSTO. Ukládá popis, který se zobrazí v seznamu nainstalovaných programů.|Žádné|  
|[&#60;formregions –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.|Žádné|  
|[&#60;formRegion&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.|`Name`|  
|[&#60;vstoruntime –&#62; Element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|Požadováno. Popisuje určitou verzi sady Visual Studio Tools for Office runtime, který je podporuje řešení pro Office.|`release`<br /><br /> `version`<br /><br /> `supportUrl`|  
  
## <a name="remarks"></a>Poznámky  
 Aplikace můžete upravit ručně a manifesty nasazení v řešeních pro systém Office. Později musíte aplikaci znovu podepsat a manifesty nasazení pomocí generování manifestu a nástroj pro úpravy (mage.exe a mageui.exe). Další informace najdete v tématu [postupy: opakované podepsání aplikace a manifesty nasazení](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="file-location"></a>Umístění souboru  
 Manifest aplikace je specifická pro jednu verzi řešení. Z tohoto důvodu by měl být manifestů aplikace ukládají odděleně od manifesty nasazení. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Umístí soubory specifické pro verzi v podadresáři s názvem podle přidružené verze v **soubory aplikace** podadresář ve složce publikování.  
  
## <a name="file-name-syntax"></a>Syntaxe názvu souboru  
 Název souboru manifestu aplikace by měl být úplný název a příponu aplikace, jako v identifikovat `assemblyIdentity` element, za nímž následuje manifest rozšíření. Manifest aplikace, který odkazuje na přizpůsobení OutlookAddIn1.dll by například použít následující syntaxe názvu souboru.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>Viz také  
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  