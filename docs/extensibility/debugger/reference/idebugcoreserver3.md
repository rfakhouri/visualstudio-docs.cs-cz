---
title: IDebugCoreServer3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCoreServer3
helpviewer_keywords: IDebugCoreServer3 interface
ms.assetid: 51f5f41b-a5a4-4df0-a703-41f3d1811d7f
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9456ddbe7588217e4864f6f8c8b994bc9323ab76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugcoreserver3"></a>IDebugCoreServer3
Toto rozhraní umožňuje přístup k informacím o serveru, který je proces spuštěný v.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugCoreServer3 : IDebugCoreServer2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementuje sady Visual Studio.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](/cpp/atl/queryinterface) k získání tohoto rozhraní z [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní. Volání [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md) mohou vracet toto rozhraní. Toto rozhraní se nejčastěji používá dodavatelem vlastní port spustit programy na serveru (místní nebo vzdálené).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod na [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní, toto rozhraní implementuje následujících metod:  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetServerName](../../../extensibility/debugger/reference/idebugcoreserver3-getservername.md)|Načte název serveru.|  
|[GetServerFriendlyName](../../../extensibility/debugger/reference/idebugcoreserver3-getserverfriendlyname.md)|Načte popisný verzi název serveru|  
|[EnableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-enableautoattach.md)|Určuje konkrétní ladění moduly automaticky připojit k procesy při spuštění těchto procesů.|  
|[DiagnoseWebDebuggingError](../../../extensibility/debugger/reference/idebugcoreserver3-diagnosewebdebuggingerror.md)|Při automatické připojení selže, načte určitý kód chyby.|  
|[CreateInstanceInServer](../../../extensibility/debugger/reference/idebugcoreserver3-createinstanceinserver.md)|Vytvoří instanci modul ladění na serveru.|  
|[QueryIsLocal](../../../extensibility/debugger/reference/idebugcoreserver3-queryislocal.md)|Získá příznak označující, zda je server na stejném počítači jako volající.|  
|[GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)|Načte hodnotu, která určuje protokol, že se používá ke komunikaci se serverem.|  
|[DisableAutoAttach](../../../extensibility/debugger/reference/idebugcoreserver3-disableautoattach.md)|Zakáže všechny automatické připojte nastavení pro všechny moduly ladění, které zná tento server.|  
  
## <a name="remarks"></a>Poznámky  
 Poskytovatel vlastní port obdrží [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) rozhraní na volání [událostí](../../../extensibility/debugger/reference/idebugportevents2-event.md). `IDebugCoreServer3` Rozhraní můžete získat z tohoto rozhraní.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)   
 [GetServer](../../../extensibility/debugger/reference/idebugdefaultport2-getserver.md)