---
title: "&lt;publisherIdentity –&gt; – Element (ClickOnce – nasazení) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
caps.latest.revision: "11"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: 9a59b97b3260beaf39ae20b62a44903add13e622
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity –&gt; – Element (ClickOnce – nasazení)
Obsahuje informace o vydavateli, který podepsal tento – manifest nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `publisherIdentity` Prvek je nutný pro podepsané manifesty. Následující tabulka znázorňuje atributy, které `publisherIdentity` element podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Popisuje identitu stranu, která publikovaná této aplikace.|  
|`issuerKeyHash`|Požadováno. Obsahuje hodnotu hash SHA-1 veřejný klíč vystavitele certifikátu.|  
  
#### <a name="parameters"></a>Parametry  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
  
## <a name="exceptions"></a>Výjimky  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
  
## <a name="subhead"></a>Dílčí hlavička