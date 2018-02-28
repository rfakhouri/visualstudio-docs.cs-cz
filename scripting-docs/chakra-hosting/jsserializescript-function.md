---
title: "Jsserializescript – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 92bc6c1de0f2cd43dfe9566413fb64188fd5a382
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsserializescript-function"></a>JsSerializeScript – funkce
Serializuje Analyzovaná skript do vyrovnávací paměti, než můžete znovu použít.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `script`  
 Skript k serializaci.  
  
 `buffer`  
 Vyrovnávací paměť pro umístění serializovaných skript do. Může mít hodnotu null.  
  
 `bufferSize`  
 Na záznam, velikost vyrovnávací paměti, v bajtech; Při ukončení velikost vyrovnávací paměti, v bajtech, požadované pro uchovávání serializovaných skriptu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 `JsSerializeScript`analyzuje skript a pak uloží analyzované formě skriptu ve formátu nezávislé na modulu runtime. Serializovaná skript pak lze deserializovat v jakékoli runtime bez nutnosti skript tak, aby se znovu Analyzovaná.  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)