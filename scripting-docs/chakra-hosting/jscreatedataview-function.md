---
title: "Jscreatedataview – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5150a9b858e09217ee7ac3c1f25efba36615f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatedataview-function"></a>JsCreateDataView – funkce
Vytvoří JavaScriptu `DataView` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayBuffer`  
 Existující `ArrayBuffer` objekt, který chcete použít jako úložiště pro výsledek `DataView` objektu.  
  
 `byteOffset`  
 Posun v bajtech od začátku `arrayBuffer` pro výsledek `DataView` k odkazu.  
  
 `byteLength`  
 Počet bajtů v ArrayBuffer pro výsledek DataView odkazovat.  
  
 `result`  
 Nový objekt zobrazení DataView.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
 Toto rozhraní API je podporována pouze v režimu okraj.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)