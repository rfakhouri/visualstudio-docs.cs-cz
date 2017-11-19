---
title: JsSerializedScriptUnloadCallback typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f485d31367f189231d354c653c8e58cc8656eb9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsserializedscriptunloadcallback-typedef"></a>JsSerializedScriptUnloadCallback – typedef
Po dokončení ke všem prostředkům týkající se spouštění skriptů, volá modulem runtime.     Volající by měl v tuto chvíli bez zdroji Pokud načíst kód bajtů a kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `sourceContext`  
 Kontext předaný `JsParseSerializedScriptWithCallback` nebo `JsRunSerializedScriptWithCallback`.  
  
## <a name="remarks"></a>Poznámky  
  
> [!WARNING]
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)