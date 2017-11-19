---
title: "Jssetexception – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsSetException
helpviewer_keywords: JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d8fce71f14dedea02e1809fb72281f575f60604
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jssetexception-function"></a>JsSetException – funkce
Nastaví modul runtime aktuální kontext do stavu výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `exception`  
 Výjimka JavaScript pro modul runtime aktuálního kontextu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `JsNoError`Pokud modul byla nastavena do stavu výjimky, kód chyby jinak.  
  
## <a name="remarks"></a>Poznámky  
 Pokud modul runtime aktuální kontext je již ve stavu výjimky, toto rozhraní API vrátí `JsErrorInExceptionState`.  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)