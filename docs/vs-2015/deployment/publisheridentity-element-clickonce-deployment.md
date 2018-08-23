---
title: '&lt;publisherIdentity&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 4c11e8ed9a3e0b4341708fc849462fbc476dc395
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668907"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; – Element (nasazení ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ &lt;publisherIdentity&gt; – Element (nasazení ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/publisheridentity-element-clickonce-deployment).  
  
Obsahuje informace o vydavateli, který podepsal manifestu nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<publisherIdentity  
   name  
   issuerKeyHash  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `publisherIdentity` Vyžádáním – element pro podepsané manifesty. V následující tabulce jsou uvedeny atributy, které `publisherIdentity` elementu podporuje.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Popisuje identity stranu, která publikovala tuto aplikaci.|  
|`issuerKeyHash`|Požadováno. Obsahuje hodnotu hash SHA-1 veřejného klíče certifikátu vystavitele.|  
  
#### <a name="parameters"></a>Parametry  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
  
## <a name="exceptions"></a>Výjimky  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
  
## <a name="subhead"></a>Podnadpis



