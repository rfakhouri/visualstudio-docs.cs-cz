---
title: Jsgetarraybufferstorage – funkce | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a667325eb4d1d9540751a52232e5e06b3004b8b5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788352"
---
# <a name="jsgetarraybufferstorage-function"></a>JsGetArrayBufferStorage – funkce
Získá základní úložiště paměti používané `ArrayBuffer`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayBuffer`  
 ArrayBuffer instance.  
  
 `buffer`  
 Vyrovnávací paměť ArrayBuffer. Doba platnosti vrácené vyrovnávací paměti je stejný jako životnost `ArrayBuffer`. Vyrovnávací paměti ukazatele nepočítá jako odkaz na `ArrayBuffer` za účelem uvolnění paměti.  
  
 `bufferLength`  
 Počet bajtů ve vyrovnávací paměti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)