---
title: IDiaSession::findInlineeLinesByRVA | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 7a74d5ee-0dbf-47c0-92b4-47ec03b13ce9
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a2d42607adfa594a2acc32a6c0650dd288867439
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49814958"
---
# <a name="idiasessionfindinlineelinesbyrva"></a>IDiaSession::findInlineeLinesByRVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte výčet, který umožňuje klientovi k iteraci v rámci o počtu řádků všech funkcí, které jsou vloženy, přímo nebo nepřímo, symbolem zadaný nadřazený prvek a jsou obsaženy v rámci zadaného relativní virtuální adresu (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findInlineeLinesByRVA (   
   IDiaSymbol*           parent,  
   DWORD                 rva,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [in] `IDiaSymbol` Představující nadřazeného objektu.  
  
 `rva`  
 [in] Určuje adresu jako adresu RVA.  
  
 `length`  
 [in] Určuje rozsah adres v počet bajtů, aby pokryl s Tento dotaz.  
  
 `ppResult`  
 [out] Obsahuje `IDiaEnumLineNumbers` objekt, který obsahuje seznam čísel řádků, které jsou načteny.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)



