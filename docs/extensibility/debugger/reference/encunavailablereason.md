---
title: EncUnavailableReason | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EncUnavailableReason
helpviewer_keywords: EncUnavailableReason enumeration
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7fe64a8c8e91535e575677d60b6d30d39fa9abf4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="encunavailablereason"></a>EncUnavailableReason
`This is for internal use only!`Představuje důvodům, **upravit a pokračovat** není k dispozici.  
  
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
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)