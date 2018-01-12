---
title: "&lt;Aktualizovat&gt; – Element (vývoj pro Office v sadě Visual Studio) | Microsoft Docs"
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
helpviewer_keywords:
- update element
- <update> element
- application manifests [Office development in Visual Studio], <update> element
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 72caa5e93b311430f4416946b6ec0bdc9fda5031
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="ltupdategt-element-office-development-in-visual-studio"></a>&lt;Aktualizovat&gt; – Element (vývoj pro Office v sadě Visual Studio)
  `update` Element určuje interval, kdy řešení zkontroluje aktualizace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<update  
  enabled>  
  <expiration  
    maximumAge  
    unit  
  />  
</update>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `update` Element je povinná a je v `vstav3` oboru názvů.  
  
 `update` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`enabled`|Požadováno. Nastavte položku povoleno na jednu z následujících hodnot:<br /><br /> -   **Hodnota TRUE,** ke kontrole aktualizací.<br />-   **false** zabránit kontrola aktualizací.|  
  
 `update` Element má následující podřízené prvky.  
  
### <a name="expiration"></a>vypršení platnosti  
 `expiration` Element je povinná a je v `vstav3` oboru názvů. Tento element určuje interval, kdy řešení kontroluje aktualizace.  
  
 `expiration` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`maximumAge`|-Vyžaduje. Nastavte toto celé číslo.|  
|`unit`|Požadováno. Nastavit `unit` na jednu z následujících hodnot:<br /><br /> -   **hodiny**<br />-   **počet dnů**<br />-   **týdny**|  
  
## <a name="example-of-always-checking-for-updates"></a>Příklad vždy kontrola aktualizací  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `update` element, který je nastaven vždy zjišťování aktualizací v řešeních pro systém Office.  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:update enabled="true" />  
```  
  
## <a name="example-of-setting-a-default-update-interval"></a>Příklad nastavení výchozí Interval aktualizace  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `update` element v manifestu aplikace pro řešení Office. Tento příklad kódu je součástí většího příkladu vztahujícího se v [manifesty aplikací pro řešení Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kód  
  
```  
<vstav3:update enabled="true">  
    <vstav3:expiration maximumAge="7" unit="days" />  
</vstav3:update>  
```  
  
## <a name="see-also"></a>Viz také  
 [Nasazení řešení Office s použitím technologie ClickOnce](../vsto/deploying-an-office-solution-by-using-clickonce.md)   
 [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty nasazení pro řešení Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce – manifest aplikace ](/visualstudio/deployment/clickonce-application-manifest)  
  
  