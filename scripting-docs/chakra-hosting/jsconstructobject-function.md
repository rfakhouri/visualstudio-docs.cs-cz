---
title: "Jsconstructobject – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsConstructObject
helpviewer_keywords: JsConstructObject function
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 505136aacebc8ae2c643842c3ff180feed66e3e6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsconstructobject-function"></a>JsConstructObject – funkce
Volá funkci jako konstruktor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `function`  
 Funkce, která má být vyvolán jako konstruktor.  
  
 `arguments`  
 Argumenty pro volání.  
  
 `argumentCount`  
 Počet argumentů funkce předaná.  
  
 `result`  
 Hodnota vrácená z volání funkce.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)