---
title: Jssetruntimebeforecollectcallback – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 469b33a324f67d17bd6f5156da7cce169b98c663
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788601"
---
# <a name="jssetruntimebeforecollectcallback-function"></a>JsSetRuntimeBeforeCollectCallback – funkce
Nastaví funkci zpětného volání, která je volána modulem runtime před uvolňování paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `runtime`  
 Modul runtime, pro které chcete zaregistrovat přidělení zpětného volání.  
  
 `callbackState`  
 Uživatel zadal stavu, který se předá zpět zpětné volání.  
  
 `beforeCollectCallback`  
 Funkce zpětného volání, nastaví se.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyvolá se zpětné volání na aktuální prováděcí vlákno runtime, proto je blokované spuštění až po dokončení zpětné volání.  
  
 Zpětné volání lze hostitelů Příprava pro uvolňování paměti. Například uvolněním nepotřebné odkazy na objekty Chakra.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)