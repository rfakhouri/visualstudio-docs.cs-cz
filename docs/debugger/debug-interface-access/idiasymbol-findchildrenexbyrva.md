---
title: IDiaSymbol::findChildrenExByRVA | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::findChildrenExByRVA
ms.assetid: cbc57c6c-7d64-4469-a114-1dd6671e5ec5
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 06892ad4d10988513b6ca4e474ccbd313577c464
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolfindchildrenexbyrva"></a>IDiaSymbol::findChildrenExByRVA
Načte podřízené objekty daného symbolu, které jsou platné v zadaný relativní virtuální adresy (RVA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findChildrenExByRVA (   
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
 [v] Určuje RVA.  
  
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