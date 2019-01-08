---
title: IDebugAsyncOperation::Start | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugAsyncOperation.Start
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugAsyncOperation::Start
ms.assetid: a7272364-28e0-48ae-8405-b8bce8a6b9fd
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 099e256496278a33ccae77351641cfdd23447b1f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54094780"
---
# <a name="idebugasyncoperationstart"></a>IDebugAsyncOperation::Start
Způsobí, že na začátek asynchronní operace.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Start(  
   IDebugAsyncOperationCallBack*  padocb  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `padocb`  
 Rozhraní zpětného volání, která bude přijímat události stavu z této operace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_UNEXPECTED`|Operace již čeká na vyřízení.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda způsobí, že `IDebugSyncOperation::Execute` asynchronně volat ve vlákně získané z `IDebugSyncOperation::GetTargetThread`. Tuto metodu lze volat pouze z vlákna ladicího programu; v opačném případě nebude vracet, dokud operace se dokončila.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAsyncOperation::Abort](../../winscript/reference/idebugasyncoperation-abort.md)   
 [Idebugasyncoperation – rozhraní](../../winscript/reference/idebugasyncoperation-interface.md)   
 [IDebugSyncOperation::Execute](../../winscript/reference/idebugsyncoperation-execute.md)   
 [IDebugSyncOperation::GetTargetThread](../../winscript/reference/idebugsyncoperation-gettargetthread.md)