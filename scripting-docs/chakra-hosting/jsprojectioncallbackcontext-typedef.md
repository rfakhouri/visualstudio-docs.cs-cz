---
title: "JsProjectionCallbackContext – definice typu | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7548dc14ab4b3dddc1633a1ba948aba564d8438a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsprojectioncallbackcontext-typedef"></a>JsProjectionCallbackContext – definice typu
Kontext předat do aplikace zpětné volání, JsProjectionEnqueueCallback, z JsRT a následně předán zpět do JsRT v zadané zpětné volání, `JsProjectionCallback`, v aplikaci na správný vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje volání `JsSetProjectionEnqueueCallback` přijímat zpětná volání.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)