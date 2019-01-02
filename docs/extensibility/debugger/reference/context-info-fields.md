---
title: CONTEXT_INFO_FIELDS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- CONTEXT_INFO_FIELDS
helpviewer_keywords:
- CONTEXT_INFO_FIELDS enumeration
ms.assetid: ef436bd3-738e-47e8-828c-8febce752439
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 532a2f309af612fb74a2f810b7fe445b79f813fc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53847953"
---
# <a name="contextinfofields"></a>CONTEXT_INFO_FIELDS
Určuje, jaké informace se mají načíst informace o kontextu paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_CONTEXT_INFO_FIELDS {   
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
typedef DWORD CONTEXT_INFO_FIELDS;  
```  
  
```csharp  
public enum enum_CONTEXT_INFO_FIELDS {  
   CIF_MODULEURL =       0x00000001,  
   CIF_FUNCTION =        0x00000002,  
   CIF_FUNCTIONOFFSET =  0x00000004,  
   CIF_ADDRESS =         0x00000008,  
   CIF_ADDRESSOFFSET =   0x00000010,  
   CIF_ADDRESSABSOLUTE = 0x00000020,  
   CIF_ALLFIELDS =       0x0000003f  
};  
```  
  
## <a name="members"></a>Členové  
 CIF_MODULEURL  
 Inicializace/použít `bstrModuleUrl` pole [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktury.  
  
 CIF_FUNCTION  
 Inicializace/použít `bstrFunction` pole `CONTEXT_INFO` struktury.  
  
 CIF_FUNCTIONOFFSET  
 Inicializace/použít `posFunctionOffset` pole `CONTEXT_INFO` struktury.  
  
 CIF_ADDRESS  
 Inicializace/použít `bstrAddress` pole `CONTEXT_INFO` struktury.  
  
 CIF_ADDRESSOFFSET  
 Inicializace/použít `bstrAddressOffset` pole `CONTEXT_INFO` struktury.  
  
 CIF_ALLFIELDS  
 Inicializace/použít všechna pole `CONTEXT_INFO` struktury.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou předány parametr [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) indikace které pole [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md) struktury mají být inicializovány.  
  
 Tyto příznaky jsou také použity k označení polí s `CONTEXT_INFO` struktury jsou používány a platný, pokud vrátí strukturu.  
  
 Tyto hodnoty lze kombinovat s bitový operátor OR.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CONTEXT_INFO](../../../extensibility/debugger/reference/context-info.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)