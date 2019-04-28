---
title: IDebugProgramNode2::GetHostMachineName_V7 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNode2::GetHostMachineName
helpviewer_keywords:
- IDebugProgramNode2::GetHostMachineName_V7
- IDebugProgramNode2::GetHostMachineNameIDebugProgramNode2::GetHostMachineName
ms.assetid: a992f2c9-f68b-4146-8cc2-027753bf7ce6
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 63e4f1a3621dde3fba5e8a2dabf45eaceb5d8ea4
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63418046"
---
# <a name="idebugprogramnode2gethostmachinenamev7"></a>IDebugProgramNode2::GetHostMachineName_V7
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

ZASTARALÉ. NEPOUŽÍVEJTE.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetHostMachineName_V7 (   
   BSTR* pbstrHostMachineName  
);  
```  
  
```csharp  
int GetHostMachineName_V7 (   
   out string pbstrHostMachineName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrHostMachineName`  
 [out] Vrátí název počítače, ve kterém je aplikace spuštěna.  
  
## <a name="return-value"></a>Návratová hodnota  
 Implementace by měla vždy vrátit `E_NOTIMPL`.  
  
## <a name="remarks"></a>Poznámky  
  
> [!WARNING]
> Od verze [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], tato metoda se už nepoužívá a by měl vždy vrátit `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
