---
title: Jssetruntimememoryallocationcallback – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 755ab36c8edb8c0350eb2b245e060344c8825dee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788637"
---
# <a name="jssetruntimememoryallocationcallback-function"></a>JsSetRuntimeMemoryAllocationCallback – funkce
Nastaví zpětné volání přidělení paměti pro zadaný modul runtime  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `runtime`  
 Modul runtime, pro které chcete zaregistrovat přidělení zpětného volání.  
  
 `callbackState`  
 Uživatel zadal stavu, který se předá zpět zpětné volání.  
  
 `allocationCallback`  
 Zpětné volání při přidělení paměti pro lze volat pro události přidělení paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Registrace zpětné volání přidělení paměti způsobí modulu runtime pro volání zpět na hostitele pokaždé, když získá paměť, nebo uvolní paměť operačního systému. Rutina zpětného volání je volána před správce paměti runtime přiděluje bloku paměti. Přidělení budou odmítnuty, pokud zpětné volání vrací hodnotu false. Po uvolnění paměti blok, a také po selhání přidělení, bude správce paměti runtime také vyvolat rutina zpětného volání.  
  
 Vyvolá se zpětné volání na aktuální prováděcí vlákno runtime, proto je blokované spuštění až po dokončení zpětné volání.  
  
 Návratová hodnota zpětné volání není uložen; dříve odmítnutých přidělení nezabrání v modulu runtime vyvolání zpětné volání později pro nové přidělení paměti.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)