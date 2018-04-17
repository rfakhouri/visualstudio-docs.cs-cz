---
title: EncUnavailableReason | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- EncUnavailableReason
helpviewer_keywords:
- EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4dcf705015925145b790b14a44007fed8d8fad3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!` Představuje důvodům, **upravit a pokračovat** není k dispozici.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum tagEncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
typedef enum tagEncUnavailableReason EncUnavailableReason;  
```  
  
```csharp  
public enum EncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 ENCUN_NONE  
 Žádný konkrétní důvod, proč upravit a pokračovat není k dispozici.  
  
 ENCUN_INTEROP  
 Upravit a pokračovat není během spolupráce volání k dispozici.  
  
 ENCUN_SQLCLR  
 Upravit a pokračovat není při volání procedury SQL, který používá Common Language Runtime (CLR) k dispozici.  
  
 ENCUN_MINIDUMP  
 Upravit a pokračovat není při zpracování malý výpis k dispozici.  
  
 ENCUN_EMBEDDED  
 Při zpracování vloženým kódem, upravit a pokračovat není k dispozici.  
  
 ENCUN_ATTACH  
 Upravit a pokračovat není k dispozici protože relace se připojil k, spuštění pomocí ladicího programu.  
  
 ENCUN_WIN64  
 Upravit a pokračovat není při zpracování kód 64bitová verze systému Windows k dispozici.  
  
## <a name="remarks"></a>Poznámky  
 Tento výčet je pro interní použití pouze pomocí [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]. [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md) a [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md) metod, jak je implementované dodavatele vlastní port musí vracet vždycky `E_NOTIMPL`.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.idl  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)