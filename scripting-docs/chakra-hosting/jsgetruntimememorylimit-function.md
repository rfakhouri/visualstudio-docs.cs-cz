---
title: "Jsgetruntimememorylimit – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords: JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6373e166ff4efe6bc8c5a33d203d60647c4be9b7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetruntimememorylimit-function"></a>JsGetRuntimeMemoryLimit – funkce
Získá aktuální limit paměti pro modul runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `runtime`  
 Modul runtime, jejichž omezení paměti je mají být načteny.  
  
 `memoryLimit`  
 Modul runtime aktuální limit paměti, v bajtech nebo -1, pokud byla nastavena žádná omezení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Limit paměti runtime může vždy být načtená bez ohledu na to, jestli je aktivní na jiné vlákno modulu runtime.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)