---
title: MODULE_SYMBOL_SEARCH_INFO | Dokumentace Microsoftu
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
- MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords:
- MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 074e837a1c0449420d7042539fb4c8dfa0396fe6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672475"
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [MODULE_SYMBOL_SEARCH_INFO](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/module-symbol-search-info).  
  
Obsahuje informace o vyhledávací cesty symbolů, které byly prohledány stavu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
  
 Pokud `bstrVerboseSearchInfo` pole není prázdné a obsahuje seznam cest prohledávat a výsledky hledání. V seznamu je formátováno s cestou, za nímž následuje symbol tří teček ("..."), za nímž následuje výsledek. Pokud existuje více než jednu dvojici výsledek cestu, každý pár oddělený pár "\r\n" (návrat na začátek řádku return nebo odřádkování). Vzor vypadá takto:  
  
 \<cesta >... \<výsledku > \r\n\<cesta >... \<výsledku > \r\n\<cesta >... \<výsledku >  
  
 Všimněte si, že poslední položka nemá \r\n pořadí.  
  
 Tady je možný výskyt `bstrVerboseSearchInfo` řetězec, který se poslal na standardní výstup.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)

