---
title: JsPromiseContinuationCallback – definice typu | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 762391cb66e5298bd70beb3238720d3717554ae0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788478"
---
# <a name="jspromisecontinuationcallback-typedef"></a>JsPromiseContinuationCallback – definice typu
Zpětné volání promise pokračování.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `task`  
  `callbackState`  
  
## <a name="remarks"></a>Poznámky  
 Hostitel může určení zpětného volání promise pokračování v `JsSetPromiseContinuationCallback`. Pokud skript vytvoří úloha se spustí později, pak zpětné volání pokračování promise bude volána s úlohy a úlohy mají být vloženy do fronty FIFO, po dokončení aktuální skriptu proběhnout provádění.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)