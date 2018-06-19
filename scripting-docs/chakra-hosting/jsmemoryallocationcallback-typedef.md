---
title: Jsmemoryallocationcallback – Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9672c23f48a2cb3e20de58012b267b30f4514d66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788517"
---
# <a name="jsmemoryallocationcallback-typedef"></a>JsMemoryAllocationCallback – Typedef
Uživatel implementována rutina zpětného volání pro události přidělení paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 callbackState  
 Stav předaný jssetruntimememoryallocationcallback –.  
  
 allocationEvent  
 Typ události typu přidělení.  
  
 allocationsize nejsou konzistentní  
 Velikost přidělení.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Pro událost JsMemoryAllocate vrácením hodnoty true umožňuje modulu runtime pokračujte s přidělení. Vrácení hodnoty false určuje, že požadavek na přidělení byl odmítnut. Návratová hodnota se ignoruje při dalších událostí, přidělení.  
  
## <a name="remarks"></a>Poznámky  
 Jssetruntimememoryallocationcallback – použijte k registraci této zpětného volání.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)