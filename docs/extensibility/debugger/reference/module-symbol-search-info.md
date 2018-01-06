---
title: MODULE_SYMBOL_SEARCH_INFO | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords: MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c4afe972f4f5218c04c1bd8a9223c7b317dc3ab3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
Obsahuje informace o cesty pro hledání symbolu, které byly prohledány stavu.  
  
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
 Kombinace příznaků z [SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md) výčtu zadání druh vyhledávání informace popsané v této struktuře.  
  
 `bstrVerboseSearchInfo`  
 Cesty pro hledání a výsledky zřetězen do jednoho řetězce.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je vrácená z volání [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md) metoda.  
  
 Pokud `bstrVerboseSearchInfo` pole není prázdný a obsahuje seznam cest vyhledávat a výsledky vyhledávání. V seznamu je naformátován s cestou, za nímž následuje třemi tečkami ("..."), za nímž následuje výsledek. Pokud existuje více než jednu dvojici výsledek cestu, každý pár jsou oddělené oddělovačem pár "\r\n" (znaků CR vrátit/konce řádku). Vzor vypadá takto:  
  
 \<cesta >... \<výsledek > \r\n\<cesta >... \<výsledek > \r\n\<cesta >... \<výsledek >  
  
 Všimněte si, že poslední položka nemá \r\n pořadí.  
  
 Tady je možného `bstrVerboseSearchInfo` řetězec, který byl odeslán do standardní na více systémů.  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)