---
title: IDebugProgramNodeAttach2::OnAttach | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugProgramNodeAttach2::OnAttach
helpviewer_keywords:
- IDebugProgramNodeAttach2::OnAttach
ms.assetid: 5fe52761-a508-4ab5-abdb-334fb6590334
caps.latest.revision: 4
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 845ec66215c5d999aaf3b5c9658bc0fb8e7295a7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148546"
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
