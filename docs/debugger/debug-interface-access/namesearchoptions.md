---
title: Namesearchoptions – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e816c559215d5662fe1a20dcad21eaf30f7667bc
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868050"
---
# <a name="namesearchoptions"></a>NameSearchOptions
Určuje možnosti hledání symbolů a názvy souborů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum NameSearchOptions {   
   nsNone,  
   nsfCaseSensitive     = 0x1,  
   nsfCaseInsensitive   = 0x2,  
   nsfFNameExt          = 0x4,  
   nsfRegularExpression = 0x8,  
   nsfUndecoratedName   = 0x10,  
  
// For backward compatibility:  
   nsCaseSensitive           = nsfCaseSensitive,  
   nsCaseInsensitive         = nsfCaseInsensitive,  
   nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,  
   nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,  
   nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive  
};  
```  
  
## <a name="elements"></a>Elementy  
 `nsNone`  
 Nejsou zadány žádné parametry.  
  
 `nsfCaseSensitive`  
 Platí shoda názvu malá a velká písmena.  
  
 `nsfCaseInsensitive`  
 Platí shoda nerozlišuje velikost písmen názvů.  
  
 `nsfFNameExt`  
 Názvy považuje za cesty a použije shodného názvu název_souboru.přípona.  
  
 `nsfRegularExpression`  
 Platí shoda názvu malá a velká písmena pomocí hvězdičky (*) a otazník (?) jako zástupné znaky.  
  
 `nsfUndecoratedName`  
 Platí jenom pro symboly, které mají nedekorovaných i dekorované názvy.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty z tento výčet se předají do následujících metod:  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)