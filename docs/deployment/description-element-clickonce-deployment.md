---
title: "&lt;Popis&gt; – Element (ClickOnce – nasazení) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords: <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
caps.latest.revision: "19"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 41fd9fcee2d0ae954f5ec234bf23cbefd5ccd6da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Popis&gt; – Element (ClickOnce – nasazení)
Identifikuje informace o aplikaci použít k vytvoření přítomnosti prostředí a **přidat nebo odebrat programy** položky v Ovládacích panelech.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `description` Element je povinná a je v `urn:schemas-microsoft-com:asm.v1` oboru názvů. Neobsahuje žádné podřízené elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`publisher`|Požadováno. Určuje název společnosti používat pro umístění ikony v systému Windows **spustit** nabídky a **přidat nebo odebrat programy** položky v Ovládacích panelech, když je nasazení nakonfigurované pro instalaci.|  
|`product`|Požadováno. Identifikuje úplný název produktu. Použít jako název ikonu nainstalovaná v systému Windows **spustit** nabídky.|  
|`suiteName`|Volitelné. Identifikuje podsložku v rámci `publisher` složku v systému Windows **spustit** nabídky.|  
|`supportUrl`|Volitelné. Určuje adresu URL podpory, které se zobrazí v **přidat nebo odebrat programy** položky v Ovládacích panelech. Pro podporu aplikace v systému Windows je taky vytvořit zástupce odkazující na tuto adresu URL **spustit** nabídky, když je nasazení nakonfigurované pro instalaci.|  
  
## <a name="remarks"></a>Poznámky  
 Element popisu je požadována všechny konfigurace nasazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `description` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. Tento příklad kódu je součástí většího příkladu vztahujícího se pro [Manifest aplikace ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.  
  
```  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)