---
title: "&lt;appAddin&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: application manifests [Office development in Visual Studio], <appAddin> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 27f286f9bde8db68a7190796f1d154a402fb208d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="ltappaddingt-element-office-development-in-visual-studio"></a>&lt;appAddin&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `appAddin` Element `vstov4` obor názvů ukládá informace specifické pro vlastní nastavení pro doplňky VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 `appAddin` Element je povinná a je v `vstov4` oboru názvů. Existuje pouze jeden `appAddin` element definovaný v manifestu aplikace.  
  
 `appAddin` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`application`|Požadováno. Identifikuje aplikaci Microsoft Office. Hodnota může být jeden z následujících: Excel, InfoPath, Outlook, PowerPoint, Project, Visio nebo Word.|  
|`loadBehavior`|Volitelné. Ve výchozím nastavení `loadBehavior` zapnutá nastavením této hodnoty na. Pro ladění, doplňku VSTO lze zakázat pomocí nastavení hodnoty na dva. Další informace najdete v tabulce s názvem LoadBehavior – hodnoty v [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|  
|`keyName`|Požadováno. Tato hodnota je název klíče registru, který se použije k načtení doplňku VSTO v aplikaci. Další informace najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).|  
  
 `appAddin` Element má následující podřízené prvky.  
  
### <a name="friendlyname"></a>FriendlyName  
 Volitelné. `friendlyName` Element je vysvětleno v [& č. 60; friendlyName & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/friendlyname-element-office-development-in-visual-studio.md).  
  
### <a name="description"></a>description  
 Volitelné. `description` Element je vysvětleno v [& č. 60; Popis & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/description-element-office-development-in-visual-studio.md).  
  
### <a name="formregions"></a>formregions –  
 Vyžaduje se jenom pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů. `formRegions` Element je vysvětleno v [& č. 60; formregions – & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/formregions-element-office-development-in-visual-studio.md).  
  
## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `appAddin` prvky v aplikaci Outlook řešení nasadit pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  