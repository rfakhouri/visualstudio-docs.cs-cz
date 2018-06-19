---
title: Jssetruntimememorylimit – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 587eb369e6971c7527177624ccf5baf839246cf9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788592"
---
# <a name="jssetruntimememorylimit-function"></a>JsSetRuntimeMemoryLimit – funkce
Nastaví aktuální limit paměti pro modul runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `runtime`  
 Modul runtime, jejichž omezení paměti je možné nastavit.  
  
 `memoryLimit`  
 Nový modul runtime limit paměti, v bajtech nebo -1 pro žádné omezení paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Limit paměti způsobí, že všechny operace, která překračuje limit k selhání s chybou "nedostatek paměti". Nastavení omezení paměti modul runtime na-1 znamená, že modul runtime nemá žádné omezení paměti. Nový výchozí runtimes na situaci, kdy žádný limit paměti. Pokud nový limit paměti je větší než aktuální využití, volání bude úspěšné a všechny budoucí přidělení v tento modul runtime selžou, dokud modul runtime využití paměti klesne pod limit.  
  
 Limit paměti runtime může vždy být nastaveno, bez ohledu na to, zda je modul runtime aktivní na jiné vlákno.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)