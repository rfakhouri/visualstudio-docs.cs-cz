---
title: "Jsnumbertodouble – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsNumberToDouble
helpviewer_keywords: JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3dba3205bcb55d3a9a233a5125a4854210b20f5d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsnumbertodouble-function"></a>JsNumberToDouble – funkce
Načte `double` hodnota číselné hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `value`  
 Číselnou hodnotu převést `double` hodnotu.  
  
 `doubleValue`  
 `double` Hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce načte hodnotu číselnou hodnotu. Se nezdaří s `JsErrorInvalidArgument` Pokud typ hodnoty není číslo.  
  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)