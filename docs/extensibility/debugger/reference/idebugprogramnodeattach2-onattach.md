---
title: IDebugProgramNodeAttach2::OnAttach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords: IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9c5a70baa682af956e6337c89b2c01b3f9c29ebd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)