---
title: Jsthreadservicecallback – Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4b7ea4d0d5eaba17269a1777cdf96b5a2a5cda3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788529"
---
# <a name="jsthreadservicecallback-typedef"></a>JsThreadServiceCallback – Typedef
Zpětné volání služby přístup z více vláken.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 zpětné volání  
 Zpětné volání pro pracovní položku pozadí.  
  
 callbackData  
 Argument data mají být předány zpětné volání.  
  
## <a name="remarks"></a>Poznámky  
 Při volání metody jscreateruntime –, můžete zadat hostitele služba vlákna na pozadí. -Li zadána, bude pozadí pracovní položky předán do daného hostitele pomocí této zpětného volání. Hostitele je očekáván na začátek spuštění pracovní položky pozadí okamžitě a vrátí hodnotu PRAVDA nebo vrátí hodnotu false, modul runtime, bude zpracovávat pracovní položku v vláken.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)