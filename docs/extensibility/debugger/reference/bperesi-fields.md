---
title: BPERESI_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BPERESI_FIELDS
helpviewer_keywords: BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 36ac591940acaed2ac8b8f92c701580d9d45f94a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="bperesifields"></a>BPERESI_FIELDS
Určuje informace, které mají být načteny o selhání rozlišení zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>Členové  
 PERESI_BPRESLOCATION  
 Inicializovat nebo použití `bpResLocation` (zarážek umístění řešení) pole [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) struktury.  
  
 BPERESI_PROGRAM  
 Inicializace nebo použití `pProgram` pole z `BP_ERROR_RESOLUTION_INFO` struktura.  
  
 BPERESI_THREAD  
 Inicializace nebo použití `pThread` pole z `BP_ERROR_RESOLUTION_INFO` struktura.  
  
 BPERESI_MESSAGE  
 Inicializace nebo použití `bstrMessage` pole z `BP_ERROR_RESOLUTION_INFO` struktura.  
  
 BPERESI_TYPE  
 Inicializovat nebo použití `dwType` (typ zarážek) pole `BP_ERROR_RESOLUTION_INFO` struktura.  
  
 BPERESI_ALLFIELDS  
 Inicializace nebo použití všechna pole `BP_ERROR_RESOLUTION_INFO` struktura.  
  
## <a name="remarks"></a>Poznámky  
 Předá jako parametr, který se [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md) metoda označíte, které pole [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md) struktura mají být inicializován.  
  
 Tyto hodnoty se také používají k označení, která pole v `BP_ERROR_RESOLUTION_INFO` struktura jsou používané a platné, pokud je vrácen této struktury.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)