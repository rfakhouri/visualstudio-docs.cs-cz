---
title: Debug.mstraceasyncoperationcompleted – funkce | Microsoft Docs
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
ms.assetid: 9b628b71-61f1-478a-857f-5e1f607db56c
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41370257042a2de50d21eba51c299198a6bfb72a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790377"
---
# <a name="debugmstraceasyncoperationcompleted-function"></a>Debug.msTraceAsyncOperationCompleted – funkce
Určuje, zda byla dokončena asynchronní operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.msTraceAsyncOperationCompleted(asyncOperationId, status)  
```  
  
#### <a name="parameters"></a>Parametry  
 `asyncOperationId`  
 Požadováno. ID přidružené k asynchronní operace.  
  
 `status`  
 Volitelné. Stav asynchronní operace. Pokud není zadaný, `Debug.MS_ASYNC_OP_STATUS_SUCCESS` se používá.  
  
## <a name="remarks"></a>Poznámky  
 Po dokončení asynchronní operace volání této funkce.  
  
 `asyncOperationId`musí odpovídat ID dříve vrácená z operace `Debug.msTraceAsyncOperationStarting`.  
  
 Možné hodnoty `status` zahrnují:  
  
-   `Debug.MS_ASYNC_OP_STATUS_SUCCESS`  
  
-   `Debug.MS_ASYNC_OP_STATUS_CANCELED`  
  
-   `Debug.MS_ASYNC_OP_STATUS_ERROR`  
  
> [!NOTE]
>  Některé nástroje pro ladění nezobrazují informace odesílané do ladicího programu.  
  
## <a name="example"></a>Příklad  
 Následující kód představuje příklad asynchronní volání pro trasování [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace.  
  
```JavaScript  
function asyncWrapperFunction() {  
    var opID = Debug.msTraceAsyncOperationStarting('async trace');  
    doSomethingAsync().then(function (result) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_SUCCESS);  
        Debug.msTraceAsyncCallbackStarting(opID);  
        // Process result of async operation.  
    }, function (error) {  
        Debug.msTraceAsyncOperationCompleted(opID, Debug.MS_ASYNC_OP_STATUS_ERROR);  
        Debug.msTraceAsyncCallbackStarting(opID);  
    });  
  
    Debug.msTraceAsyncCallbackCompleted();  
}  
  
function doSomethingAsync() {  
    return WinJS.Promise.as(true);  
}  
  
asyncWrapperFunction();  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]