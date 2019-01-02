---
title: CONNECTION_PROTOCOL | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CONNECTION_PROTOCOL
helpviewer_keywords:
- CONNECTION_PROTOCOL enumeration
ms.assetid: 99df5865-8b36-486d-9f4c-d10ae2bc688a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f619bde5d2f81b37f50a5896c13c655aaf9fd80e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907862"
---
# <a name="connectionprotocol"></a>CONNECTION_PROTOCOL
Určuje protokol, který používá ke komunikaci mezi serverem pro ladění a ladit balíček (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum tagCONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
} CONNECTION_PROTOCOL;  
```  
  
```csharp  
public enum CONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 CONNECTION_NONE  
 Žádné připojení k serveru.  
  
 CONNECTION_UNKNOWN  
 Vytvoří připojení, ale je neznámého typu.  
  
 CONNECTION_LOCAL  
 Připojení je na místním serveru.  
  
 CONNECTION_PIPE  
 Připojení je přes pojmenovaný kanál.  
  
 CONNECTION_TCPIP  
 Připojení používá protokol TCP/IP.  
  
 CONNECTION_HTTP  
 Připojení používá protokol HTTP (prostřednictvím webového serveru).  
  
 CONNECTION_OTHER  
 Vytvořilo se jiný typ připojení (Tato hodnota není aktuálně používá.).  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou vráceny z [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)