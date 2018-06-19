---
title: DISASSEMBLY_FLAGS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: dd1aa9c73fad40d07be371ad7f9b3108464aeb34
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31101359"
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
Určuje příznaky pro zpětný překlad.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_DISASSEMBLY_FLAGS {   
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
public enum enum_DISASSEMBLY_FLAGS {   
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
 Označuje, že tento pokyn je v jiném dokumentu než předchozí.  
  
 DF_DISABLED  
 Označuje, že tento pokyn nebudou provedeny.  
  
 DF_INSTRUCTION_ACTIVE  
 Označuje, že je tento pokyn jeden další pokyny spouštění (může existovat více než jeden).  
  
 DF_DATA  
 Označuje, že je tento pokyn skutečně dat (ne kód).  
  
 DF_HASSOURCE  
 Určuje, zda má tento pokyn zdroj. Některé pokyny, jako je například kód kolekce profilace nebo paměti, mít žádný odpovídající zdroj.  
  
 DF_DOCUMENT_CHECKSUM  
 Určuje, že `bstrDocumentUrl` pole obsahuje kontrolního součtu dat po adresu URL dokumentu. Naleznete v části poznámky [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) strukturu pro způsob uložení dat kontrolního součtu.  
  
## <a name="remarks"></a>Poznámky  
 Použít jako `dwFlags` členem [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md) struktury.  
  
 Tyto příznaky mohou být kombinovány s bitové `OR`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)