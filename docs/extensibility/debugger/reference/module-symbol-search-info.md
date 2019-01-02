---
title: MODULE_SYMBOL_SEARCH_INFO | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords:
- MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e6bf29280345e1029a0732d36666ceba78ba2ed
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53826663"
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
Obsahuje informace o vyhledávací cesty symbolů, které byly prohledány stavu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef struct _tagSYMBOL_SEARCH_INFO  
{  
   SYMBOL_SEARCH_INFO_FIELDS dwValidFields;  
   BSTR                      bstrVerboseSearchInfo;  
} MODULE_SYMBOL_SEARCH_INFO;  
```  
  
```csharp  
public struct MODULE_SYMBOL_SEARCH_INFO {  
   public uint   dwValidFields;  
   public string bstrVerboseSearchInfo;  
}  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwValidFields`  
 Kombinace příznaků z [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) výčet určující druh hledání informace popsané v této struktuře.  
  
 `bstrVerboseSearchInfo`  
 Cesta pro vyhledávání a výsledky, které jsou spojeny do jednoho řetězce.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácená z volání [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) metody.  
  
 Pokud `bstrVerboseSearchInfo` pole není prázdné a obsahuje seznam cest prohledávat a výsledky hledání. V seznamu je formátováno s cestou, následované třemi tečkami ("..."), za nímž následuje výsledek. Pokud existuje více než jednu dvojici výsledek cestu, každý pár oddělený pár "\r\n" (návrat na začátek řádku return nebo odřádkování). Vzor vypadá takto:  
  
 \<cesta >... \<výsledku > \r\n\<cesta >... \<výsledku > \r\n\<cesta >... \<výsledku >  
  
 Všimněte si, že poslední položka nemá \r\n pořadí.  
  
 Tady je možný výskyt `bstrVerboseSearchInfo` řetězec, který se poslal na standardní výstup.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)