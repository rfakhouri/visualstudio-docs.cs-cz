---
title: Jsbeforecollectcallback – Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50e2b79ceb2809aee0348bae594e8494596b6089
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788163"
---
# <a name="jsbeforecollectcallback-typedef"></a>JsBeforeCollectCallback – Typedef
Zpětné volání je volána před provedením kolekce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 callbackState  
 Stav předaný JsSetBeforeCollectCallback.  
  
## <a name="remarks"></a>Poznámky  
 Použijte JsSetBeforeCollectCallback k registraci této zpětného volání.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)