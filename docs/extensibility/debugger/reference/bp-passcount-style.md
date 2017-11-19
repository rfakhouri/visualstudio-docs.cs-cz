---
title: BP_PASSCOUNT_STYLE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BP_PASSCOUNT_STYLE
helpviewer_keywords: BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 58baa5aca9ef5bddf5d7060fdc88022952bc9ce3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
Určuje podmínku, související s počtem průchodu zarážek, který způsobuje, že zarážek má provést.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>Členové  
 BP_PASSCOUNT_NONE  
 Určuje styl počet průchodu bez zarážek.  
  
 BP_PASSCOUNT_EQUAL  
 Nastavuje styl počet průchodu zarážek na. Zarážce aktivuje se v případě, že počet časy, kdy je průchodu zarážkou se rovná počtu průchodu.  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 Nastaví styl zarážek průchodu počet větší nebo rovno. Zarážce aktivuje se v případě, že počet, který je průchodu zarážkou je rovna nebo větší než počet průchodu.  
  
 BP_PASSCOUNT_MOD  
 Určuje modulo předat count. Například, pokud je tento počet průchodu typu `BP_PASSCOUNT_MOD` a předejte počet hodnota je 4, aktivuje zarážek pokaždé, když počet přístupů není násobkem 4.  
  
## <a name="remarks"></a>Poznámky  
 Použít pro `stylePassCount` členem [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) struktura, která je členem skupiny [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)