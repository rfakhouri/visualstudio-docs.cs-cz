---
title: DISASSEMBLY_FLAGS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- DISASSEMBLY_FLAGS
helpviewer_keywords:
- DISASSEMBLY_FLAGS enumeration
ms.assetid: c1ec5a4d-5d42-4660-932c-7348550140cb
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85c5e4a5b0cc5dbdcff5750ce5c87d170bb9bd20
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666575"
---
# <a name="disassemblyflags"></a>DISASSEMBLY_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [DISASSEMBLY_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/disassembly-flags).  
  
Určuje příznaky pro převod do strojového jazyka.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisassemblyData](../../../extensibility/debugger/reference/disassemblydata.md)

