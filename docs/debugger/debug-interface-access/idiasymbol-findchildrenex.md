---
title: IDiaSymbol::findChildrenEx | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::findChildrenEx
ms.assetid: 6e045045-da8c-4338-9423-81a1ca20c405
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 184c4ff637d281ba8bca15c16d3112dff4b6f96f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolfindchildrenex"></a>IDiaSymbol::findChildrenEx
Načte podřízené objekty daného symbolu. Lokální symboly, které jsou vráceny obsahují informace rozsah za provozu, pokud je program kompilovat s optimalizace na.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findChildrenEx (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `symtag`  
 [v] Určuje symbol značky podřízených prvků mají být načteny, jak jsou definovány v [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md). Nastavte na `SymTagNull` pro všechny podřízené objekty mají být načteny.  
  
 `name`  
 [v] Určuje název podřízených prvků mají být načteny. Nastavte na `NULL` pro všechny podřízené objekty mají být načteny.  
  
 `compareFlags`  
 [v] Určuje možnosti porovnání má být použita na odpovídajícím názvem. Hodnoty z [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčet může být použito samostatně nebo v kombinaci.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` pokud alespoň jednu podřízenou symbolu nalezena, nebo vrátí `S_FALSE` Pokud nebyly nalezeny žádné podřízené objekty; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je rozšířené verze [idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia100.dll  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)