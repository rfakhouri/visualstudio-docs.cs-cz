---
title: DISASSEMBLY_FLAGS | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7b0e4f793b0dcfe7a8a35bfeb06a3acd53c969d5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53960987"
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
Určuje příznaky pro převod do strojového jazyka.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
typedef DWORD DISASSEMBLY_FLAGS;  
```  
  
```csharp  
public enum enum_DISASSEMBLY_FLAGS {   
   DF_DOCUMENTCHANGE     = 0x00000001,  
   DF_DISABLED           = 0x00000002,  
   DF_INSTRUCTION_ACTIVE = 0x00000004,  
   DF_DATA               = 0x00000008,  
   DF_HASSOURCE          = 0x00000010,  
   DF_DOCUMENT_CHECKSUM  = 0x00000020  
};  
```  
  
## <a name="members"></a>Členové  
 DF_DOCUMENTCHANGE  
 Označuje, že tento pokyn je v jiném dokumentu než ta předchozí.  
  
 DF_DISABLED  
 Označuje, že tento pokyn nebude provedeno.  
  
 DF_INSTRUCTION_ACTIVE  
 Označuje, že je tento pokyn jeden další pokyny, který se spustí (může existovat více než jeden).  
  
 DF_DATA  
 Označuje, že tento pokyn je ve skutečnosti data (ne kódu).  
  
 DF_HASSOURCE  
 Označuje, že tento pokyn má zdroj. Některé pokyny, jako je například profilace nebo uvolňování paměti kolekce kód, mít žádný odpovídající zdroj.  
  
 DF_DOCUMENT_CHECKSUM  
 Označuje, že `bstrDocumentUrl` pole obsahovat data kontrolních součtů za adresu URL dokumentu. V části poznámky [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) strukturu pro způsob uložení dat kontrolního součtu.  
  
## <a name="remarks"></a>Poznámky  
 Použít jako `dwFlags` člena [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury.  
  
 Tyto příznaky lze kombinovat pomocí logické bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)