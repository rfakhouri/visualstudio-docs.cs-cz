---
title: CANSTOP_REASON | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CANSTOP_REASON
helpviewer_keywords: CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98b1e4a9db18490079dd443cb296481aed64376a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="canstopreason"></a>CANSTOP_REASON
Použít k určení, pokud program můžete zastavit provádění po dosažení do konkrétního bodu v provádění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>Členové  
 CANSTOP_ENTRYPOINT  
 Určuje vstupní bod daného programu.  
  
 CANSTOP_STEPIN  
 Určuje zanoříte se do funkce.  
  
## <a name="remarks"></a>Poznámky  
 Předat jako argument k [getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metoda potvrďte s relace ladění Manager (SDM), pokud je to v pořádku zastavit po dosažení vstupního bodu programu nebo po zanoříte se do funkci nebo metodu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)