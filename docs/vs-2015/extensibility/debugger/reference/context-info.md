---
title: CONTEXT_INFO | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f4e8c1b438cd2fa2721e81f055695e5836c26d12
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179938"
---
# <a name="contextinfo"></a>CONTEXT_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Tato struktura popisuje místní paměti nebo kontext kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 Kombinace příznaků z mu [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) výčet, který určuje, která pole jsou vyplněna<strong>.</strong>  
  
 bstrModuleUrl  
 Název modulu, ve kterém se nachází kontextu.  
  
 bstrFunction  
 Název funkce, kde se nachází kontextu.  
  
 posFunctionOffset  
 A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) strukturu, která identifikuje posun řádku a sloupci funkce přidružený kód kontextu.  
  
 bstrAddress  
 Adresa v kódu, kde se nachází daném kontextu.  
  
 bstrAddressOffset  
 Posun adresy v kódu, kde se nachází daném kontextu.  
  
 bstrAddressAbsolute  
 Absolutní adresa v paměti, kde se nachází daném kontextu.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácená z volání [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) metody.  
  
 Typickým použitím tato struktura je v podporu **paměti** okno ladění.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
