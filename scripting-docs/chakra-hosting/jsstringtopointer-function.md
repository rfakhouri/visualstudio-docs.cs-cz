---
title: "Jsstringtopointer – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsStringToPointer
helpviewer_keywords: JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ff84f929833941fed9a709497dc615189c39386
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsstringtopointer-function"></a>JsStringToPointer – funkce
Načte řetězec ukazatel hodnotu řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `value`  
 Řetězcovou hodnotu převést na řetězec ukazatel.  
  
 `stringValue`  
 Řetězec ukazatel.  
  
 `stringLength`  
 Délka řetězce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce načte řetězec ukazatel hodnotu řetězce. Se nezdaří s `JsErrorInvalidArgument` Pokud typ hodnota není řetězec. Doba platnosti řetězce, který vrátil bude být stejný jako životnost hodnoty, které pochází ze, ale ukazatel řetězec nepovažuje odkaz na hodnotu (a tak nebude bránily jeho shromažďovaných).  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)