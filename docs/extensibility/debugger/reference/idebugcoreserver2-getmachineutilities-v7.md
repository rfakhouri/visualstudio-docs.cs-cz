---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: bf5881dabea216d7226e731c169dd97d1460c7fb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
Tato metoda získá nástroje počítače pro server.  
  
> [!NOTE]
>  Tato metoda je zastaralá: Nepoužívejte ([!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] vždy vrátí hodnotu `E_NOTIMPL` Pokud tato metoda je volána). Ho se uchovávají historických důvodů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppUtil`  
 [out] Vrátí `IDebugMDMUtil2_V7` rozhraní, které představuje informace nástroje pro počítač.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí hodnotu `E_NOTIMPL`, která určuje, že metoda není implementována.  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]vždy vrátí hodnotu `E_NOTIMPL` Pokud tato metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)