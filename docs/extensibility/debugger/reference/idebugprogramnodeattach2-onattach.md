---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c7c7e6f7ef640b192b7ed8c57ac87375a5ad189
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
Připojí k přidružený program nebo odkládat údaje proces připojit [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT OnAttach(  
   [in] REFGUID guidProgramId  
);  
```  
  
```csharp  
int OnAttach(  
   ref Guid guidProgramId  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 `guidProgramId`  
 [v] `GUID` přiřadit přidružený program.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) neměla být volána metoda. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána v průběhu procesu připojování před [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána. `OnAttach` Metoda můžete provést samotný proces připojení (v takovém případě tato metoda vrátí hodnotu `S_FALSE`) nebo odložení proces připojit `IDebugEngine2::Attach` – metoda ( `OnAttach` metoda vrátí `S_OK`). V obou případech `OnAttach` metoda můžete nastavit `GUID` laděné do programu danou `GUID`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)