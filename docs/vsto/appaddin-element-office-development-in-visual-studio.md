---
title: '&lt;appAddin&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <appAddin> element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 572de1a3fccf9b66000d82e14f7895ab5cf0029f
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2018
ms.locfileid: "52304868"
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; – element (vývoj pro Office v sadě Visual Studio)
  **AppAddin** elementu `vstov4` obor názvů ukládá informace specifické pro přizpůsobení pro doplňky VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml 
<appAddin  
  application  
  loadBehavior  
  keyName>  
  <friendlyName>  
  <description>  
  <formRegions></formRegions>  
</appAddin>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 **AppAddin** element je povinný a je v `vstov4` oboru názvů. Existuje pouze jeden **appAddin** element definovaný v manifestu aplikace.  
  
 **AppAddin** element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|**Aplikace**|Požadováno. Identifikuje aplikaci Microsoft Office. Hodnota může být jeden z následujících: Excel, InfoPath, Outlook, PowerPoint, projekt, Visia nebo Word.|  
|**LoadBehavior**|Volitelné. Ve výchozím nastavení **loadBehavior** se povoluje nastavením této hodnoty. Pro ladění doplňku VSTO lze zakázat nastavením této hodnoty na dva. Další informace najdete v tabulce s názvem hodnotách LoadBehavior v [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|  
|**Název klíče**|Požadováno. Tato hodnota je název klíče registru, který se použije k načtení doplňku VSTO aplikací. Další informace najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|  
  
 **AppAddin** element má následující podřízené prvky.  
  
### <a name="friendlyname"></a>FriendlyName  
 Volitelné. **FriendlyName** element je podrobně [ &#60;friendlyName&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>description  
 Volitelné. **Popis** element je podrobně [ &#60;popis&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formregions –  
 Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO, které zahrnují oblasti formuláře. **FormRegions** element je podrobně [ &#60;formRegions&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje **appAddin** prvky v aplikaci Outlook řešení nasazeným v rámci [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```xml  
<vstov4:appAddIn   
  application="Outlook"   
  loadBehavior="3"   
  keyName="ContosoOutlookAddIn">  
  <vstov4:friendlyName>  
    ContosoOutlookAddIn  
  </vstov4:friendlyName>  
  <vstov4:description>  
    ContosoOutlookAddIn - Outlook VSTO Add-in   
    created with Visual Studio Tools for Office  
  </vstov4:description>  
  <vstov4:formRegions>  
    <vstov4:formRegion  
        name="OutlookAddIn1.FormRegion1">  
      <vstov4:messageClass name="IPM.Note" />  
      <vstov4:messageClass name="IPM.Contact" />  
      <vstov4:messageClass name="IPM.Appointment" />  
    </vstov4:formRegion>  
  </vstov4:formRegions>  
</vstov4:appAddIn>  
```  
  
## <a name="see-also"></a>Viz také:  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  
  