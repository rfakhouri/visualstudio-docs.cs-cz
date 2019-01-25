---
title: PROCESS_INFO | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- PROCESS_INFO
helpviewer_keywords:
- PROCESS_INFO structure
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9ab05d85b55fd293b648603f067d135f703aff5e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54765449"
---
# <a name="processinfo"></a>PROCESS_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Obsahuje informace o procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct tagPROCESS_INFO {   
   PROCESS_INFO_FIELDS Fields;  
   BSTR                bstrFileName;  
   BSTR                bstrBaseName;  
   BSTR                bstrTitle;  
   AD_PROCESS_ID       ProcessId;  
   DWORD               dwSessionId;  
   BSTR                bstrAttachedSessionName;  
   FILETIME            CreationTime;  
   PROCESS_INFO_FLAGS  Flags;  
} PROCESS_INFO;  
```  
  
```csharp  
public struct PROCESS_INFO {   
   public uint          Fields;  
   public string        bstrFileName;  
   public string        bstrBaseName;  
   public string        bstrTitle;  
   public AD_PROCESS_ID ProcessId;  
   public uint          dwSessionId;  
   public string        bstrAttachedSessionName;  
   public FILETIME      CreationTime;  
   public uint          Flags;  
};  
```  
  
## <a name="members"></a>Členové  
 Pole  
 Kombinace příznaků z [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) výčet určující, která pole jsou vyplněna.  
  
 bstrFileName  
 Úplná cesta a název procesu. Ekvivalentní volání [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) metody s parametrem `GN_FILENAME`.  
  
 bstrBaseName  
 Název souboru a příponu procesu. Ekvivalentní volání `IDebugProcess2::Getname` metody s parametrem `GN_BASENAME`.  
  
 bstrTitle  
 Název procesu, pokud existuje. Ekvivalentní volání `IDebugProcess2::Getname` metody s parametrem `GN_TITLE`.  
  
 ID procesu  
 [AD_PROCESS_ID](../../../extensibility/debugger/reference/ad-process-id.md) strukturu, která identifikuje procesu. Ekvivalentní volání [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) metody.  
  
 dwSessionId  
 Identifikátor, na kterém běží tento proces v relaci ladění.  
  
 bstrAttachedSessionName  
 Název připojené relaci. Ekvivalentní volání [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) metody.  
  
 CreationTime  
 Čas vytvoření procesu.  
  
 Příznaky  
 Kombinace příznaků z [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) výčet, který určit vlastnosti procesu.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je předán [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) metody, kde je vyplněna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROCESS_INFO_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)   
 [PROCESS_INFO_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)   
 [GetName –](../../../extensibility/debugger/reference/idebugprocess2-getname.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)
