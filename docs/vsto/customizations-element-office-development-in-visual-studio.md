---
title: '&lt;přizpůsobení&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <customizations> element
- customizations element
- application manifests [Office development in Visual Studio], <customizations> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ef7aa93494ef2b2a33ab4533e217bd37ccd07420
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="ltcustomizationsgt-element-office-development-in-visual-studio"></a>&lt;přizpůsobení&gt; – element (vývoj pro Office v sadě Visual Studio)
  `customizations` Element `vstov4` obor názvů obsahuje všechny informace o instalaci a načítání každé řešení Office.  
  
## <a name="syntax-for-document-level-customizations"></a>Syntaxe pro úpravy na úrovni dokumentů  
  
```xml
<customizations>  
  <customization  
    id  
    <document  
      solutionId  
    />  
  </customization>  
</customizations>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>Syntaxe pro doplňky VSTO  
  
```xml
<customizations>  
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
</customizations>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `customizations` Element obsahuje konkrétní informace o každé řešení Office. Tento element musí být v oboru názvů následující: `vstov4=urn:schemas-microsoft-com:vsto.v4`. Podřízené elementy sestavení musí také být v tomto oboru názvů.  
  
 `customizations` Element nemá žádné atributy.  
  
 `customizations` Element má následující podřízený element.  
  
### <a name="customization"></a>Přizpůsobení  
 Požadováno. `customization` Element v `vstov4` obor názvů je definován v [ &#60;přizpůsobení&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/customization-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>Příklad přizpůsobení na úrovni dokumentu  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `customizations` element pro přizpůsobení na úrovni dokumentu.  
  
> [!NOTE]  
>  Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```xml
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
    <vstov4:document   
      solutionId="73e" />  
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="example-of-an-vsto-add-in"></a>Příklad doplňku VSTO  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `customizations` element pro doplňku VSTO. Toto je VSTO pro Outlook doplněk, který zahrnuje oblasti formuláře. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```xml
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
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
</vstov4:customizations>  
```  
  
## <a name="see-also"></a>Viz také  
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace](/visualstudio/deployment/clickonce-application-manifest)  
  
  