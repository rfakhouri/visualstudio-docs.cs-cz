---
title: Idiasession::findchildren – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findChildren method
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8292dc1e88a3421b24b820c5607158799d4c7cd0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindchildren"></a>IDiaSession::findChildren
Načte všechny podřízené objekty zadaný nadřazený identifikátor odpovídající název a symbol typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `parent`  
 [v] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) představující nadřazený objekt. Pokud tento symbol nadřazené se funkce, modul nebo bloku, pak se vrátí podřízené lexikální `ppResult`. Pokud je nadřazený symbol je typu, jsou vráceny podřízené třídy. Pokud tento parametr je `NULL`, pak `symtag` musí být nastavena na `SymTagExe` nebo `SymTagNull`, která vrací globálním oboru (soubor .exe).  
  
 `symtag`  
 [v] Určuje symbol značky podřízených prvků mají být načteny. Z hodnot, která [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) výčtu. Nastavte na `SymTagNull` načíst všechny podřízené objekty.  
  
 `name`  
 [v] Určuje název podřízených prvků mají být načteny. Nastavte na `NULL` pro všechny podřízené objekty mají být načteny.  
  
 `compareFlags`  
 [v] Určuje možnosti porovnání použita na odpovídajícím názvem. Hodnoty z [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčet může být použito samostatně nebo v kombinaci.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md) načíst objekt, který obsahuje seznam podřízenými symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak najít místní proměnné funkce `pFunc` tento název shodu `szVarName`.  
  
```C++  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## <a name="see-also"></a>Viz také  
 [Přehled](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)