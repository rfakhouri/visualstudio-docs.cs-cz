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
ms.assetid: bdd5dbf7-ddda-4ef6-9db5-1fb4405261a0
caps.latest.revision: "24"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 1733ac8333675975bb5d4b42dce9df3c01e5ac0f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
  