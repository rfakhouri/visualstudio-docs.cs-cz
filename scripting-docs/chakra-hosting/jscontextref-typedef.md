---
title: Jscontextref – Typedef | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec1300717b59c3b901665b39ca0102988e83e853
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788217"
---
# <a name="jscontextref-typedef"></a>JsContextRef – Typedef
Odkaz na skript kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef JsRef JsContextRef;  
```  
  
## <a name="remarks"></a>Poznámky  
 Každý skript kontext obsahuje vlastní globální objekt liší od globální objekt v jiných kontextech skriptu.  
  
 Mnoho Chakra rozhraní API pro hostování vyžadují kontextu "aktivní" skript, který se dá nastavit pomocí `JsSetCurrentContext`. Hostování rozhraní API, které vyžadují aktuální kontext nastavit chakra bude Všimněte si, že explicitně v jejich dokumentaci.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)