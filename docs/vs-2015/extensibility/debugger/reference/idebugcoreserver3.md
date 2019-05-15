---
title: IDebugCoreServer3 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugCoreServer3
helpviewer_keywords:
- IDebugCoreServer3 interface
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cd1781b133b4c3ee95b4207a0dd237e2dd7298a1
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685653"
---
# <a name="idebugcoreserver3"></a>IDebugCoreServer3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní poskytuje přístup k informacím o serveru, který je proces spuštěn v.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Visual Studio implementuje toto rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) získat z tohoto rozhraní [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní. Volání [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) také může vrátit toto rozhraní. Toto rozhraní se nejčastěji používá dodavatelem port. Tento vlastní port spustit programy na serveru (místní nebo vzdálené).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|Načte název serveru.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|Načte verzi popisný název serveru|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|Určuje konkrétní ladicími stroji automaticky připojit k procesům při spuštění těchto procesů.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|Získá konkrétní kód chyby, když automatické připojení selže.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|Vytvoří instanci ladicího stroje na serveru.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|Získá příznak označující, zda je server na stejném počítači jako volající.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|Načte hodnotu, která se používá ke komunikaci se serverem protokolu.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|Zakáže všechny automatické připojení nastavení pro všechny ladicí stroj, který tento server ví o.|  
  
## <a name="remarks"></a>Poznámky  
 Poskytovatel port. Tento vlastní port obdrží [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní volání [události](../../../extensibility/debugger/reference/idebugportevents2-event.md). `IDebugCoreServer3` Rozhraní můžete získat z tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)
