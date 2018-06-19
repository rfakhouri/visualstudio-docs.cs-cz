---
title: Debug.mstraceasynccallbackstarting – funkce | Microsoft Docs
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
ms.assetid: 0e2ca7c4-103c-44f2-b76c-102fb1e42543
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49203cdf16e7cbd74493c882d9cf17b7629da79a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790383"
---
# <a name="debugmstraceasynccallbackstarting-function"></a>Debug.msTraceAsyncCallbackStarting – funkce
Přidruží zásobníku zpětného volání dříve určené asynchronní operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.msTraceAsyncCallbackStarting(asyncOperationId)  
```  
  
#### <a name="parameters"></a>Parametry  
 `asyncOperationId`  
 Požadováno. ID přidružené k asynchronní operace.  
  
## <a name="remarks"></a>Poznámky  
 Volání této funkce ve funkci zpětného volání pro asynchronní operaci po volání `Debug.msTraceAsyncOperationCompleted`.  
  
> [!NOTE]
>  Některé nástroje pro ladění nezobrazují informace odesílané do ladicího programu.  
  
 `asyncOperationId`musí odpovídat názvu operace předtím vrátila z `Debug.msTraceAsyncOperationStarting`.  
  
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