---
title: CONTEXT_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 46168fefd491aeeae05c6406bd2b985fc5649bd1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="contextinfo"></a>CONTEXT_INFO
Tato struktura popisuje kontextu paměti nebo kontext kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagCONTEXT_INFO {   
   CONTEXT_INFO_FIELDS dwFields;  
   BSTR                bstrModuleUrl;  
   BSTR                bstrFunction;  
   TEXT_POSITION       posFunctionOffset;  
   BSTR                bstrAddress;  
   BSTR                bstrAddressOffset;  
   BSTR                bstrAddressAbsolute;  
} CONTEXT_INFO;  
```  
  
```csharp  
public struct CONTEXT_INFO {  
   public uint          dwFields;  
   public string        bstrModuleUrl;  
   public string        bstrFunction;  
   public TEXT_POSITION posFunctionOffset;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrAddressAbsolute;  
};  
```  
  
## <a name="members"></a>Členové  
 dwFields  
 Kombinace příznaků z mu [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) výčet, který určuje pole, která jsou doplnit**.**  
  
 bstrModuleUrl  
 Název modulu, kde se nachází kontextu.  
  
 bstrFunction  
 Název funkce, kde je umístěn daný kontext.  
  
 posFunctionOffset  
 A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) struktura, která identifikuje posun řádku a ve sloupci funkce spojený s kontextem kódu.  
  
 bstrAddress  
 Adresa v kódu, kde se nachází daném kontextu.  
  
 bstrAddressOffset  
 Posun adresu v kódu, kde se nachází daném kontextu.  
  
 bstrAddressAbsolute  
 Absolutní adresa v paměti, kde se nachází daném kontextu.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácená z volání [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) metoda.  
  
 Typické použití tato struktura je v podporu **paměti** okno ladění.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)