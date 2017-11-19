---
title: "Jssetprojectionenqueuecallback – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8abdc575c5066ade4a700a0c88e09e3476a65366
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jssetprojectionenqueuecallback-function"></a>JsSetProjectionEnqueueCallback – funkce
Nastaví zpětné volání pro použití při vyvolání projekce dokončení zpět na požadované volající vlákno.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <a name="parameters"></a>Parametry  
 `projectionEnqueueContext`  
 Zpětné volání, která bude volána, když projekce dokončení proběhne vlákna na pozadí.  
  
 `callbackState`  
 V kontextu aplikace poskytované `projectionEnqueueContext`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
 Volání by měl být pocházející z různých apartment COM nebo z jiného vlákna ve stejném modelu MTA.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
> [!CAUTION]
>  PInvoke není aktuálně podporován pro toto rozhraní API.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)