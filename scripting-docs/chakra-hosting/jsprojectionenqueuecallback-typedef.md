---
title: "JsProjectionEnqueueCallback – definice typu | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bda4a3a80edac38ab2c3885c2256cdf9d03eb8c1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsprojectionenqueuecallback-typedef"></a>JsProjectionEnqueueCallback – definice typu
Zpětného volání aplikace, která je volána metodou JsRT při projekci rozhraní API byla dokončena v jiném podprocesu než byl původní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `jsCallback`  
 Zpětné volání má být volána v původní vlákno.  
  
 `jsContext`  
 Kontext aplikace.  
  
 `callbackState`  
 JsRT kontext, který musí být předán do `jsCallback`.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje volání jssetprojectionenqueuecallback – přijímat zpětná volání.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)