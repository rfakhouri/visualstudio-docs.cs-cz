---
title: "&lt;přizpůsobení&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <customization> element
ms.assetid: a3bf7f35-bd98-4530-9226-46489cd37bb1
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 922e68a676f1f8ceac547983436c76ac01facc3b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomizationgt-element-office-development-in-visual-studio"></a>&lt;přizpůsobení&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `customization` Element `vstov4` obor názvů popisuje konkrétní řešení Office. Podřízené elementy se liší pro přizpůsobení na úrovni dokumentu a doplňků VSTO.  
  
## <a name="syntax-for-document-level-customizations"></a>Syntaxe pro úpravy na úrovni dokumentů  
  
```  
<customization  
  id  
  <document  
    solutionId  
  />  
</customization>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>Syntaxe pro doplňky VSTO  
  
```  
<customization  
  id  
  <appAddin  
    application  
    loadBehavior  
    keyName>  
  <friendlyName></friendlyName>  
  <description></description>  
  <formRegions></formRegions>  
</customization>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `customization` Element obsahuje informace o přizpůsobení. Tento element musí být v oboru názvů následující: `vstov4=urn:schemas-microsoft-com:vsto.v4`. Existuje `customization` element pro každé řešení Office. Například pokud nasadíte tři řešení pro systém Office v vícenásobného projektu nasazení, existují tři `customization` elementy v manifestu aplikace.  
  
 Podřízené elementy sestavení musí také být v tomto oboru názvů.  
  
 `customization` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`id`|Vyžaduje se pro nasazení vícenásobného projektu. `id` Element jednoznačně identifikuje řešení Office.|  
  
### <a name="document-level-customizations"></a>Přizpůsobení na úrovni dokumentu  
 `customization` Element má následující podřízený element.  
  
#### <a name="document"></a>dokument  
 `document` Element v `vstov4` obor názvů je definován v [& č. 60; dokument & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/document-element-office-development-in-visual-studio.md).  
  
### <a name="vsto-add-ins"></a>Doplňků VSTO  
 `customization` Element má následující podřízený element.  
  
#### <a name="appaddin"></a>appAddin  
 `appAddin` Element v `vstov4` obor názvů je definován v [& č. 60; appAddin & č. 62; Element &#40; vývoj pro Office v sadě Visual Studio &#41; ](../vsto/appaddin-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `customization` element pro přizpůsobení na úrovni dokumentu. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:customization>  
  <vstov4:document   
    solutionId="73e" />  
</vstov4:customization>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `customization` element pro doplňku VSTO. Toto je VSTO pro Outlook doplněk, který zahrnuje oblasti formuláře. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstov4:customization>  
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
</vstov4:customization>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  