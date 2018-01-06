---
title: DISASSEMBLY_STREAM_FIELDS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DISASSEMBLY_STREAM_FIELDS
helpviewer_keywords: DISASSEMBLY_STREAM_FIELDS enumeration
ms.assetid: cfc9b4de-c756-4844-bea7-d9f186a51d1b
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1629e2665d3b02bebba35583561df49d6fdac221
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="disassemblystreamfields"></a>DISASSEMBLY_STREAM_FIELDS
Určuje, jaké informace načíst o pole zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
typedef DWORD DISASSEMBLY_STREAM_FIELDS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_STREAM_FIELDS {   
   DSF_ADDRESS          = 0x00000001,  
   DSF_ADDRESSOFFSET    = 0x00000002,  
   DSF_CODEBYTES        = 0x00000004,  
   DSF_OPCODE           = 0x00000008,  
   DSF_OPERANDS         = 0x00000010,  
   DSF_SYMBOL           = 0x00000020,  
   DSF_CODELOCATIONID   = 0x00000040,  
   DSF_POSITION         = 0x00000080,  
   DSF_DOCUMENTURL      = 0x00000100,  
   DSF_BYTEOFFSET       = 0x00000200,  
   DSF_FLAGS            = 0x00000400,  
   DSF_OPERANDS_SYMBOLS = 0x00010000,  
   DSF_ALL              = 0x000107ff  
};  
```  
  
## <a name="members"></a>Členové  
 DSF_ADDRESS  
 Inicializace nebo pomocí `bstrAddress` pole.  
  
 DSF_ADDRESSOFFSET  
 Inicializace nebo pomocí `bstrAddressOffset` pole.  
  
 DSF_CODEBYTES  
 Inicializace nebo pomocí `bstrCodeBytes` pole.  
  
 DSF_OPCODE  
 Inicializace nebo pomocí `bstrOpCode` pole.  
  
 DSF_OPERANDS  
 Inicializace nebo pomocí `bstrOperands` pole.  
  
 DSF_SYMBOL  
 Inicializace nebo pomocí `bstrSymbol` pole.  
  
 DSF_CODELOCATIONID  
 Inicializace nebo pomocí `uCodeLocationId` pole.  
  
 DSF_POSITION  
 Inicializace nebo pomocí `posBeg` a `posEnd` pole.  
  
 DSF_DOCUMENTURL  
 Inicializace nebo pomocí `bstrDocumentUrl` pole.  
  
 DSF_BYTEOFFSET  
 Inicializace nebo pomocí `dwByteOffset` pole.  
  
 DSF_FLAGS  
 Inicializace nebo pomocí `dwFlags` ([DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)) pole.  
  
 DSF_OPERANDS_SYMBOLS  
 Zahrnout názvy symbolů v `bstrOperands` pole.  
  
 DSF_ALL  
 Určuje všechna pole pro datový proud zpětný překlad.  
  
## <a name="remarks"></a>Poznámky  
 Předány jako parametr, který se [čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md) metoda označíte, které pole [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktura mají být inicializován.  
  
 Použít pro `dwFields` členem `DisassemblyData` struktura označuje pole, která je platná a použitá při vrácení strukturu.  
  
 Tyto hodnoty mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)   
 [Pro čtení](../../../extensibility/debugger/reference/idebugdisassemblystream2-read.md)   
 [DISASSEMBLY_FLAGS](../../../extensibility/debugger/reference/disassembly-flags.md)