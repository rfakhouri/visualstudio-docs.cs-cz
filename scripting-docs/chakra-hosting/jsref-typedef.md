---
title: "Jsref – Typedef | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9d4c478a45f53e83dfa59fdde21cfa4c988c92e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsref-typedef"></a>JsRef – Typedef
Odkaz na objekt vlastníkem garbage collector v Chakra.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef void *JsRef;  
```  
  
## <a name="remarks"></a>Poznámky  
 Modul runtime Chakra bude automaticky sledovat jsref – odkazy, dokud jsou uložené v místní proměnné nebo v parametrech (tj. v zásobníku). Ukládání jsref – někde jinak než v zásobníku vyžaduje volání jsaddref – a jsrelease – ke správě životnosti objektu, jinak bude systém uvolňování může uvolnit objekt, i když je stále používáno.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)