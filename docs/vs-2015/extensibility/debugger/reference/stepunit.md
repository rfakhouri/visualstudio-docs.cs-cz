---
title: STEPUNIT | Dokumentace Microsoftu
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
- STEPUNIT
helpviewer_keywords:
- STEPUNIT enumeration
ms.assetid: cb8441f2-f744-4e73-acfe-ae8542df9649
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: adb9324cbc7a87e79a91d17d4a39f5a23c9679a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670754"
---
# <a name="stepunit"></a>STEPUNIT
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [STEPUNIT](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/stepunit).  
  
Určuje jednotku kroku pro procházení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_STEPUNIT {   
   STEP_STATEMENT   = 0,  
   STEP_LINE        = 1,  
   STEP_INSTRUCTION = 2  
};  
typedef DWORD STEPUNIT;  
```  
  
```csharp  
enum enum_STEPUNIT {   
   STEP_STATEMENT   = 0,  
   STEP_LINE        = 1,  
   STEP_INSTRUCTION = 2  
};  
```  
  
## <a name="members"></a>Členové  
 STEP_STATEMENT  
 Kroky příkazem.  
  
 STEP_LINE  
 Kroky po řádku.  
  
 STEP_INSTRUCTION  
 Kroky podle instrukce.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [krok](../../../extensibility/debugger/reference/idebugprocess3-step.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Krok](../../../extensibility/debugger/reference/idebugprocess3-step.md)

