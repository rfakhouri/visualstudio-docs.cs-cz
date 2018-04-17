---
title: IDiaSymbol::findChildrenExByVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::findChildrenExByVA
ms.assetid: 29080009-36e4-4697-acd7-50f2e3e1bf1b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bbc050bf1923e13678e4938f04b40f8db30c12f2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolfindchildrenexbyva"></a>IDiaSymbol::findChildrenExByVA
Načte podřízené objekty daného symbolu, které jsou platné v zadané virtuální adresy.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findChildrenExByVA (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   DWORD             address,  
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
  
 `address`  
 [v] Určuje virtuální adresu.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` pokud alespoň jednu podřízenou symbolu nalezena, nebo vrátí `S_FALSE` Pokud nebyly nalezeny žádné podřízené objekty; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Lokální symboly, které jsou vráceny obsahovat informace o rozsahu za provozu.  
  
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