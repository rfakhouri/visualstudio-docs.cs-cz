---
title: Debug.msupdateasynccallbackrelation – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee6a1efc-375c-4ce8-a4e8-8896ee29f849
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c47ed7f6313646dddf86dd766d7f1027b2d38ad
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790374"
---
# <a name="debugmsupdateasynccallbackrelation-function"></a>Debug.msUpdateAsyncCallbackRelation – funkce
Aktualizuje stav relace mezi synchronní pracovní položkou a přidružené asynchronní operaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.msUpdateAsyncCallbackRelation(relatedAsyncOperationId, relationType)  
```  
  
#### <a name="parameters"></a>Parametry  
 `relatedAsyncOperationId`  
 Požadováno. ID přidružené k asynchronní operace.  
  
 `relationType`  
 Volitelné. Hodnota, která určuje stav relace.  
  
## <a name="remarks"></a>Poznámky  
 Synchronní pracovní položky je obvykle funkce zpětného volání pro asynchronní operace. Tato funkce může být volána po asynchronní operace byla přerušena, když se používá operace spojení, nebo v jiných scénářích.  
  
 Možné hodnoty `relationType` zahrnují:  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`  
  
-   `Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`  
  
 Další informace najdete v tématu [ladění konstanty](../../javascript/reference/debug-constants.md).  
  
> [!NOTE]
>  Některé nástroje pro ladění nezobrazují informace odesílané do ladicího programu pomocí této funkce.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]