---
title: NameSearchOptions | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7ceadd085a3099721e73e04dd09ea5a0b81ad1d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
  
-   [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)  
  
-   [Idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dia2.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [Idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md)