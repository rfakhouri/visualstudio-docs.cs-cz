---
title: Jsgetandclearexception – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e7e4f89bac59aa776762586ab20fa831b5c24bf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788331"
---
# <a name="jsgetandclearexception-function"></a>JsGetAndClearException – funkce
Vrací výjimku, která způsobila modul runtime aktuální kontext, který má být ve stavu výjimky a obnoví stav výjimky pro tento modul runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `exception`  
 Výjimka pro modul runtime aktuálního kontextu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud modul runtime aktuálním kontextu není ve stavu výjimky, toto rozhraní API vrátí `JsErrorInvalidArgument`. Pokud je zakázána modul runtime, tato možnost vrátí výjimku, která určuje, že byl ukončen skript, ale jeho nebude clear – výjimka (výjimku budou vymazána, pokud modul runtime je znovu povolit pomocí `JsEnableRuntimeExecution`).  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)