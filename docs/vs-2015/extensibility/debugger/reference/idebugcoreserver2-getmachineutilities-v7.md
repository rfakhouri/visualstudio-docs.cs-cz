---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c6d615a24e9c6608713699904724a62d14569ee4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54753607"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda načte počítač nástroje pro server.  
  
> [!NOTE]
>  Tato metoda je zastaralá: Nepoužívejte ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána). Je zachován z historických důvodů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetMachineUtilities_V7(  
   IDebugMDMUtil2_V7** ppUtil  
);  
```  
  
```csharp  
int GetMachineUtilities_V7(  
   out IDebugMDMUtil2_V7 ppUtil  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppUtil`  
 [out] Vrátí `IDebugMDMUtil2_V7` rozhraní, které představuje informace o počítači nástroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí `E_NOTIMPL`, která udává, že metoda není implementována.  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
