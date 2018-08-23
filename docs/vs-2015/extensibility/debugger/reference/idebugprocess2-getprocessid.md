---
title: IDebugProcess2::GetProcessId | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugProcess2::GetProcessId
helpviewer_keywords:
- IDebugProcess2::GetProcessId
ms.assetid: d5b6f03c-d49d-4b83-b072-016ac3124f5f
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2f44a35e3204e71ec37805dcc35711d6f38785d7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669486"
---
# <a name="idebugprocess2getprocessid"></a>IDebugProcess2::GetProcessId
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugProcess2::GetProcessId](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocess2-getprocessid).  
  
Získá identifikátor GUID pro tento proces.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetProcessId(  
   GUID* pguidProcessId  
);  
```  
  
```csharp  
int GetProcessId(  
   out Guid pguidProcessId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pguidProcessId`  
 [out] Vrátí identifikátor GUID pro tento proces.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Globálně jedinečný identifikátor (GUID) identifikuje tento proces ze všech dalších procesů spuštěných v systému.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)

