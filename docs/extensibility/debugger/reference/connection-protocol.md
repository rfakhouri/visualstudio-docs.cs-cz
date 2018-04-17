---
title: CONNECTION_PROTOCOL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: e1e1dc8cd22b529eafd6183578be7de6ffe69549
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="connectionprotocol"></a>CONNECTION_PROTOCOL
Určuje protokol, který používá ke komunikaci mezi serverem pro ladění a ladění balíčku (DE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum tagCONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
} CONNECTION_PROTOCOL;  
```  
  
```csharp  
public enum CONNECTION_PROTOCOL {  
   CONNECTION_NONE    = 0,  
   CONNECTION_UNKNOWN = 1,  
   CONNECTION_LOCAL   = 2,  
   CONNECTION_PIPE    = 3,  
   CONNECTION_TCPIP   = 4,  
   CONNECTION_HTTP    = 5,  
   CONNECTION_OTHER   = 6  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 CONNECTION_NONE  
 Provedl se žádné připojení k serveru.  
  
 CONNECTION_UNKNOWN  
 Bylo vytvořeno připojení, ale je neznámého typu.  
  
 CONNECTION_LOCAL  
 Připojení je místní server.  
  
 CONNECTION_PIPE  
 Připojení je přes pojmenovaný kanál.  
  
 CONNECTION_TCPIP  
 Připojení používá protokol TCP/IP.  
  
 CONNECTION_HTTP  
 Připojení používá protokol HTTP (prostřednictvím webového serveru).  
  
 CONNECTION_OTHER  
 Jiný typ připojení bylo úspěšně navázáno. (Tato hodnota není právě používána.).  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou vráceny z [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetConnectionProtocol](../../../extensibility/debugger/reference/idebugcoreserver3-getconnectionprotocol.md)