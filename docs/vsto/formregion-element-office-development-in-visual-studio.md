---
title: "&lt;formRegion&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
helpviewer_keywords: application manifests [Office development in Visual Studio], <formRegion> element
ms.assetid: d397cf31-c0ef-47f0-860a-cd816e4bf6eb
caps.latest.revision: "23"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: bc425459cee4b4398ead78939283ab4db6efc134
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;formRegion&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `formRegion` Element `vstov4` obor názvů identifikuje oblasti formuláře aplikace Microsoft Office Outlook, která souvisí s doplňku VSTO.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<formRegion  
  name>  
  <messageClass  
    name/>  
</formRegion>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `formRegion` Element `vstov4` obor názvů identifikuje oblasti formuláře, který je přidružen doplňku VSTO v Outlooku. Je vyžadována pouze pro aplikaci Outlook doplňků VSTO obsahující oblasti formulářů.  
  
 Může být více `formRegion` elementy definované uvnitř `formRegions` element pro jeden Add-in VSTO.  
  
 `formRegion` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Určuje název oblasti formuláře.|  
  
 `formRegion` Element má následující podřízené prvky.  
  
### <a name="messageclass"></a>Třída messageClass  
 `messageClass` Element identifikuje formuláře aplikace Outlook, který je přidružen oblasti formuláře.  
  
 `messageClass` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Identifikuje formulář, který je přidružen oblasti formuláře.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `formRegion` element v manifestu aplikace pro Outlook VSTO doplňku nasadit pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Existují tři zpráva třídy přidružené k této oblasti jednoho formuláře. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
```  
<vstov4:formRegion  
    name="OutlookAddIn1.FormRegion1">  
  <vstov4:messageClass name="IPM.Note" />  
  <vstov4:messageClass name="IPM.Contact" />  
  <vstov4:messageClass name="IPM.Appointment" />  
</vstov4:formRegion>  
```  
  
## <a name="see-also"></a>Viz také  
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  