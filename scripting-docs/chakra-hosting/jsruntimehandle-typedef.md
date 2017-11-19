---
title: "Jsruntimehandle – Typedef | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3c0344e203c58691048c55ba4080c6c86c1c643
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="jsruntimehandle-typedef"></a>JsRuntimeHandle – Typedef
Popisovač pro Chakra runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef void *JsRuntimeHandle;  
```  
  
## <a name="remarks"></a>Poznámky  
 Každý Chakra runtime má svou vlastní modul pro vykonání nezávislé, JIT kompilátoru a shromážděných halda paměti. Každý modul runtime jako takový je naprosto izolované od jiné moduly runtime.  
  
 Moduly runtime lze použít v jakékoli vlákno, ale pouze jedno vlákno můžete volat do modul runtime kdykoli.  
  
> [!WARNING]
>  Jsruntimehandle – na rozdíl od jiných odkazy na objekty v Chakra hostující rozhraní API, není paměti shromáždit, protože obsahuje shromážděných halda paměti sám sebe. Modul runtime, budou i nadále existovat, dokud se nazývá jsdisposeruntime –.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jsrt.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)