---
title: IDebugProgramNodeAttach2::OnAttach | Dokumentace Microsoftu
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
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 4
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 10409c4fcab6c2d7352a654996c764e0a2f17332
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49830467"
---
# <a name="idebugprogramnodeattach2onattach"></a>IDebugProgramNodeAttach2::OnAttach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Připojí se k programu přidružené nebo odloží procesu připojování k [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] `GUID` přiřazení k přidružené aplikaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) by neměla být volána metoda. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána před během procesu připojování [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána. `OnAttach` Metoda můžete provést samotný proces připojení (v takovém případě tato metoda vrátí `S_FALSE`) nebo odložit procesu připojování k `IDebugEngine2::Attach` – metoda ( `OnAttach` vrátí metoda `S_OK`). V obou případech `OnAttach` metoda můžete nastavit `GUID` k laděnému programu daný `GUID`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgramNodeAttach2](../../../extensibility/debugger/reference/idebugprogramnodeattach2.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)

