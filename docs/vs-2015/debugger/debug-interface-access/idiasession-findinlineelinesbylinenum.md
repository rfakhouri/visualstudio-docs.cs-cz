---
title: IDiaSession::findInlineeLinesByLinenum | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ecd508c98a8a40ea6f89b4d2054326c5794af6a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669490"
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaSession::findInlineeLinesByLinenum](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasession-findinlineelinesbylinenum).  
  
Načte výčet, který umožňuje klientovi k iteraci v rámci informace o číslech řádků všech funkcí, které jsou vloženy, přímo nebo nepřímo v zadaný zdrojový soubor a číslo řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `compiland`  
 [in] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který reprezentuje kompilace, ve kterém chcete hledat čísla řádků. Tento parametr nemůže mít `NULL`.  
  
 `file`  
 [in] [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) objekt, který reprezentuje zdrojový soubor, ve kterých chcete hledat. Tento parametr nemůže mít `NULL`.  
  
 `linenum`  
 [in] Určuje číslo řádku založen na jedničce.  
  
> [!NOTE]
>  Nula nelze použít k určení všech řádků (použít [idiasession::findlines –](../../debugger/debug-interface-access/idiasession-findlines.md) metody k vyhledání všech řádků).  
  
 `column`  
 [in] Určuje číslo sloupce. Můžete určit všechny sloupce nula. Sloupec je posun bajtů do řádku.  
  
 `ppResult`  
 [out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam čísel řádků, které byly načteny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)



