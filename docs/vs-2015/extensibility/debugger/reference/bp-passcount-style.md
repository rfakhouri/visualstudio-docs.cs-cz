---
title: BP_PASSCOUNT_STYLE | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- BP_PASSCOUNT_STYLE
helpviewer_keywords:
- BP_PASSCOUNT_STYLE structure
ms.assetid: 0a647047-e2d5-4724-a0b8-68108425ecad
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: deb4ce7c464e8518faff55957e1873ef1cd92c39
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754256"
---
# <a name="bppasscountstyle"></a>BP_PASSCOUNT_STYLE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje podmínku, počet průchodu zarážky, který způsobí, že zarážka má provést, přidružené.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
typedef DWORD BP_PASSCOUNT_STYLE;  
```  
  
```csharp  
public enum enum_BP_PASSCOUNT_STYLE {   
   BP_PASSCOUNT_NONE             = 0x0000,  
   BP_PASSCOUNT_EQUAL            = 0x0001,  
   BP_PASSCOUNT_EQUAL_OR_GREATER = 0x0002,  
   BP_PASSCOUNT_MOD              = 0x0003  
};  
```  
  
## <a name="members"></a>Členové  
 BP_PASSCOUNT_NONE  
 Určuje styl počet pass bez zarážek.  
  
 BP_PASSCOUNT_EQUAL  
 Nastaví styl počet průchodu zarážky rovno. Zarážka je vyvoláno, pokud počet pokusů, které je zarážka dosažena rovná počtu průchodu.  
  
 BP_PASSCOUNT_EQUAL_OR_GREATER  
 Nastaví styl počet průchodu zarážky na stejné nebo větší. Zarážka aktivuje se v případě, že počet pokusů, které je zarážka dosažena je roven nebo větší než počet pass.  
  
 BP_PASSCOUNT_MOD  
 Určuje, počet průchodů modulo. Například, pokud je počet průchodu typu `BP_PASSCOUNT_MOD` a je hodnota počtu průchodu 4, aktivována zarážka pokaždé, když je počet průchodů násobek čísla 4.  
  
## <a name="remarks"></a>Poznámky  
 Používá pro `stylePassCount` člena [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) struktura, která je členem skupiny [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) a [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) struktury.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)
