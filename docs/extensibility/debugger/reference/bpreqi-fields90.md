---
title: BPREQI_FIELDS90 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BPREQI_FIELDS90 enumeration
ms.assetid: bf6f7efc-39f2-46a2-906d-c3647bf89995
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 496f529118f44ec573983362d792b0c68213b05b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bpreqifields90"></a>BPREQI_FIELDS90
Vytvoří výčet platné hodnoty, které zadejte informace o žádosti o zarážek mají být načteny. Tento výčet rozšiřuje [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BPREQI_FIELDS90  
{  
   // VS 8.0 values  
   BPREQI90_BPLOCATION                = 0x0001,  
   BPREQI90_LANGUAGE                  = 0x0002,  
   BPREQI90_PROGRAM                   = 0x0004,  
   BPREQI90_PROGRAMNAME               = 0x0008,  
   BPREQI90_THREAD                    = 0x0010,  
   BPREQI90_THREADNAME                = 0x0020,  
   BPREQI90_PASSCOUNT                 = 0x0040,  
   BPREQI90_CONDITION                 = 0x0080,  
   BPREQI90_FLAGS                     = 0x0100,  
   BPREQI90_ALLOLDFIELDS              = 0x01ff,  
   BPREQI90_VENDOR                    = 0x0200,  
   BPREQI90_CONSTRAINT                = 0x0400,  
   BPREQI90_TRACEPOINT                = 0x0800,  
  
   // Values added in VS 9.0  
   BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
   BPREQI90_ALLFIELDS                 = 0xffff  
};  
typedef DWORD BPREQI_FIELDS90;  
```  
  
```csharp  
public enum enum_BPREQI_FIELDS90  
{  
    // VS 8.0 values  
    BPREQI90_BPLOCATION                = 0x0001,  
    BPREQI90_LANGUAGE                  = 0x0002,  
    BPREQI90_PROGRAM                   = 0x0004,  
    BPREQI90_PROGRAMNAME               = 0x0008,  
    BPREQI90_THREAD                    = 0x0010,  
    BPREQI90_THREADNAME                = 0x0020,  
    BPREQI90_PASSCOUNT                 = 0x0040,  
    BPREQI90_CONDITION                 = 0x0080,  
    BPREQI90_FLAGS                     = 0x0100,  
    BPREQI90_ALLOLDFIELDS              = 0x01ff,  
    BPREQI90_VENDOR                    = 0x0200,  
    BPREQI90_CONSTRAINT                = 0x0400,  
    BPREQI90_TRACEPOINT                = 0x0800,  
  
    // Values added in VS 9.0  
    BPREQI90_MACROTRACEPOINT           = 0x1000,  
  
    BPREQI90_ALLFIELDS                 = 0xffff  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 BPREQI90_BPLOCATION  
 Inicializace nebo použít `bpLocation` (zarážek umístění) pole [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) nebo [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktura.  
  
 BPREQI90_LANGUAGE  
 Inicializace nebo použít `guidLanguage` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_PROGRAM  
 Inicializace nebo použít `pProgram` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_PROGRAMNAME  
 Inicializace nebo použít `bstrProgramName` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_THREAD  
 Inicializace nebo použít `pThread` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_THREADNAME  
 Inicializace nebo použít `bstrThreadName` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_PASSCOUNT  
 Inicializace nebo použít `bpPassCount` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_CONDITION  
 Inicializace nebo použijte `bpCondition` (podmínka zarážek) pole `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktura.  
  
 BPREQI90_FLAGS  
 Inicializace nebo použít `dwFlags` pole z `BP_REQUEST_INFO` nebo `BP_REQUEST_INFO2` struktury.  
  
 BPREQI90_ALLOLDFIELDS  
 Inicializace nebo použít pro všechna pole v z `BP_REQUEST_INFO` struktura.  
  
 BPREQI90_VENDOR  
 Inicializace nebo použít `guidVendor` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI90_CONSTRAINT  
 Inicializace nebo použít `bstrConstraint` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI90_TRACEPOINT  
 Inicializace nebo použít `bstrTracepoint` pole z `BP_REQUEST_INFO2` struktura.  
  
 BPREQI90_MACROTRACEPOINT  
 Inicializace nebo použít `bstrMacroTracepoint` pole z `BP_REQUEST_INFO2` struktura. BPREQI_ALLFIELDS toto pole neobsahuje.  
  
 BPREQI90_ALLFIELDS  
 Určuje pro všechna pole `BP_REQUEST_INFO2` struktura.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)