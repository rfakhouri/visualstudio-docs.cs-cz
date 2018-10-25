---
title: IDebugCoreServer2::GetMachineUtilities_V7 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
helpviewer_keywords:
- IDebugCoreServer2::GetMachineUtilities_V7
ms.assetid: 64c1f08f-853b-4498-9810-29791581ef2f
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ecb460a070038d5a107f559e88be38381b11869c
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49822290"
---
# <a name="idebugcoreserver2getmachineutilitiesv7"></a>IDebugCoreServer2::GetMachineUtilities_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato metoda načte počítač nástroje pro server.  
  
> [!NOTE]
>  Tato metoda je zastaralá: Nepoužívejte ([!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána). Je zachován z historických důvodů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [out] Vrátí `IDebugMDMUtil2_V7` rozhraní, které představuje informace o počítači nástroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vždy vrátí `E_NOTIMPL`, která udává, že metoda není implementována.  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] vždy vrátí `E_NOTIMPL` Pokud tato metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)

