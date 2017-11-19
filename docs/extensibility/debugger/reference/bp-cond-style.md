---
title: BP_COND_STYLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_COND_STYLE
helpviewer_keywords: BP_COND_STYLE enumeration
ms.assetid: a93b1412-f447-48a1-af9d-38f3dbb3092f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a2dd89bd7e70e619bea5f1f2cb17b70e98eecaf3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bpcondstyle"></a>BP_COND_STYLE
Určuje styl zarážek podmínku pro čekající na vyřízení a vázaný zarážky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
typedef DWORD BP_COND_STYLE;  
```  
  
```csharp  
public enum enum_BP_COND_STYLE {   
   BP_COND_NONE         = 0x0000,  
   BP_COND_WHEN_TRUE    = 0x0001,  
   BP_COND_WHEN_CHANGED = 0x0002  
};  
```  
  
## <a name="members"></a>Členové  
 BP_COND_NONE  
 Zarážce aktivuje, když je dosaženo zarážek na pozici. Není zadaná žádná podmínka zarážek.  
  
 BP_COND_WHEN_TRUE  
 Aktivuje zarážce, jen když podmíněným výrazem přidružené zarážce vyhodnocuje `true`.  
  
 BP_COND_WHEN_CHANGED  
 Aktivuje se zarážek jenom v případě, že hodnota podmíněného výrazu spojené se zarážkou bylo změněno z jeho předchozího vyhodnocení.  
  
## <a name="remarks"></a>Poznámky  
 Použít pro `styleCondition` členem [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)