---
title: FRAMEINFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- FRAMEINFO
helpviewer_keywords:
- FRAMEINFO structure
ms.assetid: 95001b89-dddb-45bb-889d-8327994e38a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4080a0d868f154136b11058abdf29948a353b0ba
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31104199"
---
# <a name="frameinfo"></a>FRAMEINFO
Popisuje rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct tagFRAMEINFO {   
   FRAMEINFO_FLAGS    m_dwValidFields;  
   BSTR               m_bstrFuncName;  
   BSTR               m_bstrReturnType;  
   BSTR               m_bstrArgs;  
   BSTR               m_bstrLanguage;  
   BSTR               m_bstrModule;  
   UINT64             m_addrMin;  
   UINT64             m_addrMax;  
   IDebugStackFrame2* m_pFrame;  
   IDebugModule2*     m_pModule;  
   BOOL               m_fHasDebugInfo;  
   BOOL               m_fStaleCode;  
   BOOL               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
```csharp  
public struct FRAMEINFO {   
   public uint              m_dwValidFields;  
   public string            m_bstrFuncName;  
   public string            m_bstrReturnType;  
   public string            m_bstrArgs;  
   public string            m_bstrLanguage;  
   public string            m_bstrModule;  
   public ulong             m_addrMin;  
   public ulong             m_addrMax;  
   public IDebugStackFrame2 m_pFrame;  
   public IDebugModule2     m_pModule;  
   public int               m_fHasDebugInfo;  
   public int               m_fStaleCode;  
   public int               m_fAnnotatedFrame;  
} FRAMEINFO;  
```  
  
## <a name="members"></a>Členové  
 m_dwValidFields  
 Kombinace příznaků z [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md) výčet, který určuje, které jsou vyplněna.  
  
 m_bstrFuncName  
 Název funkce související s rámce zásobníku.  
  
 m_bstrReturnType  
 Návratový typ přidružené rámce zásobníku.  
  
 m_bstrArgs  
 Argumenty funkce související s rámce zásobníku.  
  
 m_bstrLanguage  
 Jazyk, ve kterém je funkce implementována.  
  
 m_bstrModule  
 Název modulu přidružený rámce zásobníku.  
  
 m_addrMin  
 Adresa minimální fyzické zásobníku.  
  
 m_addrMAX  
 Adresa maximální fyzické zásobníku.  
  
 m_pFrame  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objekt, který představuje tuto rámce zásobníku.  
  
 m_pFrame  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) objekt, který představuje modul, který obsahuje tento rámce zásobníku.  
  
 m_fHasDebugInfo  
 Nenulová (`TRUE`) Pokud informace o ladění existuje v daném snímku.  
  
 m_fHasDebugInfo  
 Nenulová (`TRUE`) Pokud rámce zásobníku je spojen s kódem, který již není platný.  
  
 m_fHasDebugInfo  
 Nenulová (`TRUE`) Pokud je rámec zásobníku poznámkou správcem ladicí relace (SDM).  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předána [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md) metoda k vyplnění. Tato struktura je také obsažena v seznamu, který je součástí [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md) rozhraní, které je zase, vrácena z volání [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [FRAMEINFO_FLAGS](../../../extensibility/debugger/reference/frameinfo-flags.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugstackframe2-getinfo.md)   
 [IEnumDebugFrameInfo2](../../../extensibility/debugger/reference/ienumdebugframeinfo2.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)