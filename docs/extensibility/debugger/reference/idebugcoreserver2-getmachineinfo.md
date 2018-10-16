---
title: IDebugCoreServer2::GetMachineInfo | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugCoreServer2::GetInfo
helpviewer_keywords:
- IDebugCoreServer2::GetInfo
ms.assetid: 8fa1a1d3-9fcb-4fb3-bf4e-e7172ac08d77
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fdb79a91dcd90e34f7673255eaf8b71e681cd025
ms.sourcegitcommit: e680e8ac675f003ebcc8f8c86e27f54ff38da662
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2018
ms.locfileid: "49356688"
---
# <a name="idebugcoreserver2getmachineinfo"></a>IDebugCoreServer2::GetMachineInfo
Načte popis, který core server běží na počítače.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMachineInfo(   
   MACHINE_INFO_FIELDS Fields,  
   MACHINE_INFO*       pMachineInfo  
);  
```  
  
```csharp  
int GetMachineInfo(   
   enum_ MACHINE_INFO_FIELDS  Fields,  
   MACHINE_INFO[]             pMachineInfo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `Fields`  
 [in] Kombinace příznaků z [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md) výčtu, která pole zadáte `pMachineInfo` mají doplnit.  
  
 `pMachineInfo`  
 [out v] A [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md) struktura, která se vyplní popis počítače.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [MACHINE_INFO_FIELDS](../../../extensibility/debugger/reference/machine-info-fields.md)   
 [MACHINE_INFO](../../../extensibility/debugger/reference/machine-info.md)
