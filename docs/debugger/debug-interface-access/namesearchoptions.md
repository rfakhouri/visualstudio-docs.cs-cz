---
title: NameSearchOptions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4a6a4237e806a6906ef984cd942e027fe7d9227d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="namesearchoptions"></a>NameSearchOptions
Určuje možnosti hledání názvů symbol a souborů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum NameSearchOptions {   
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
 Nejsou zadány žádné možnosti.  
  
 `nsfCaseSensitive`  
 Platí malá a velká písmena název odpovídají.  
  
 `nsfCaseInsensitive`  
 Platí velká a malá písmena název odpovídají.  
  
 `nsfFNameExt`  
 Zpracovává názvy jako cesty a použije název odpovídají název_souboru.přípona.  
  
 `nsfRegularExpression`  
 Se vztahuje malá a velká písmena název odpovídají pomocí hvězdičky (*) a otazníku (?) jako zástupné znaky.  
  
 `nsfUndecoratedName`  
 Platí pouze pro symboly, které mají upraveného i dekorované názvy.  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty z tento výčet jsou předávány následujících metod:  
  
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