---
title: IDebugProcessSecurity | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- IDebugProcessSecurity interface
ms.assetid: 8a52ddca-bd99-49c0-9778-469dce7abd44
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7e34a93e73bd1c4c9b5e70f89d318c2db6a84f2b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967953"
---
# <a name="idebugprocesssecurity"></a>IDebugProcessSecurity
`IDebugProcessSecurity` je implementováno dodavatele portu uživatele upozornit, že není bezpečné připojování k procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProcessSecurity : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugProcessSecurity`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetUserName](../../../extensibility/debugger/reference/idebugprocesssecurity-getusername.md)|Získá uživatelské jméno od dodavatele portu.|  
|[QueryCanSafelyAttach](../../../extensibility/debugger/reference/idebugprocesssecurity-querycansafelyattach.md)|Uživatele upozorňuje, že není bezpečné připojení k ladění procesu.|  
  
## <a name="remarks"></a>Poznámky  
 Implementace tohoto rozhraní zobrazí upozornění a umožnění uživateli zrušit, pokud proces, ke kterému se připojuje může považovány za nebezpečné.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Porty](../../../extensibility/debugger/ports.md)   
 [Dodavatelé portů](../../../extensibility/debugger/port-suppliers.md)   
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)