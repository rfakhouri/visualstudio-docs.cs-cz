---
title: Konstanty pro ladění | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 76b572ee-bad0-404e-9fd4-841c9af35642
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e2c50181dc9f40d8665d6caca407232231682d63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790353"
---
# <a name="debug-constants"></a>Konstanty pro ladění
Ladění konstanty návratový konstantní hodnoty, které jsou vlastnosti `Debug` objektu.  
  
## <a name="debug-object-constants"></a>Objekt konstanty pro ladění  
 Následující tabulka uvádí konstantní hodnoty, které jsou vlastnosti [objektu Debug](../../javascript/reference/debug-object-javascript.md).  
  
|Konstanta|Popis|Hodnota|  
|--------------|-----------------|-----------|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ASSIGN_DELEGATE`|Synchronní pracovní položka přiřazena zpětného volání nebo pokračování ke spuštění asynchronní operace.|0|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_JOIN`|Synchronní pracovní položka splněné součástí asynchronní operace spojení.|1|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CHOOSEANY`|Synchronní pracovní položka splněné volba asynchronní operaci.|2|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_CANCEL`|Synchronní pracovní položka byla zrušena.|3|  
|`Debug.MS_ASYNC_CALLBACK_STATUS_ERROR`|Synchronní pracovní položka způsobila chybu v asynchronní operace.|4|  
|`Debug.MS_ASYNC_OP_STATUS_SUCCESS`|Asynchronní operace byla úspěšná.|1|  
|`Debug.MS_ASYNC_OP_STATUS_CANCELED`|Asynchronní operace byla zrušena.|2|  
|`Debug.MS_ASYNC_OP_STATUS_ERROR`|Asynchronní operaci za následek chybu.|3|  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Debug.mstraceasyncoperationcompleted – funkce](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md)   
 [Debug.msupdateasynccallbackrelation – funkce](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md)