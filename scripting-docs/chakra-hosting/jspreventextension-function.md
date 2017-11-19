---
title: "Jspreventextension – funkce | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsPreventExtension
helpviewer_keywords: JsPreventExtension function
ms.assetid: 8da07e20-d076-4ae4-9fb0-3f3c141518c2
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 81f059bb3d0c6054fbfc3cca2aee4e84d0fa01d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jspreventextension-function"></a>JsPreventExtension – funkce
Umožňuje objektu bez extensible.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDAPI_(JsErrorCode) JsPreventExtension(  
   _In_ JsValueRef object  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Objekt, aby bez extensible.  
  
## <a name="return-value"></a>Návratová hodnota  
 Kód `JsNoError` v případě, že byla operace úspěšná, jinak kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Vyžaduje aktivní kontext skriptu.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)