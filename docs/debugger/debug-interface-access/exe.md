---
title: Exe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- .dll files
- Exe symbol
- .exe files
- executable files, Exe symbol
ms.assetid: a781d2cf-55fe-4373-9cf1-b732864244e0
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab02eacffe01c267a2f3d4ff463b729591bb8b19
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="exe"></a>Exe
Exe je jediným symbolů bez buď lexikální nebo třídy nadřazeným prvkem, jako reprezentuje globálním oboru souboru .exe nebo .dll. Je jen jeden symbol `SymTagExe` značky na soubor. [Idiasession::get_globalscope –](../../debugger/debug-interface-access/idiasession-get-globalscope.md) metoda vrátí symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_age –](../../debugger/debug-interface-access/idiasymbol-get-age.md)|`DWORD`|Stáří tento spustitelný soubor.|  
|[Idiasymbol::get_guid –](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|`GUID`|`GUID`tohoto spustitelného souboru.|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|`BOOL`|`TRUE`Pokud soubor symbol přidružený tento spustitelný soubor obsahuje typy C (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_isstripped –](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|`BOOL`|`TRUE`Pokud soukromých symbolů mít bylo provedeno oříznutí ze souboru symbol přidružený tento spustitelný soubor (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_machinetype –](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|`DWORD`|Hodnota označující cílový procesor (jeden z [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) hodnoty).|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|`BSTR`|Název souboru .exe.|  
|[Idiasymbol::get_signature –](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|`DWORD`|Podpis spustitelného souboru.|  
|[Idiasymbol::get_symbolsfilename –](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|`BSTR`|Úplná cesta k souboru PDB nebo dbg soubor .exe.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagExe` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
  
## <a name="see-also"></a>Viz také  
 [Idiasession::get_globalscope –](../../debugger/debug-interface-access/idiasession-get-globalscope.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)