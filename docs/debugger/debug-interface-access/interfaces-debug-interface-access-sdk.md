---
title: "Rozhraní (přístup k rozhraní SDK ladění) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interfaces [DIA SDK]
- DIA SDK, interfaces
ms.assetid: 62aee7c3-d314-4272-a32b-b2818f32fab8
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 044c6ce1dafbd5ce753d9e3a98d41ed1963a77ee
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="interfaces-debug-interface-access-sdk"></a>Rozhraní (Přístup k rozhraní ladění SDK)
Metody jsou abecední v rámci každé rozhraní v tabulce obsahu a na stránce rozhraní v tabulce Vtable pořadí.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Idiaaddressmap –](../../debugger/debug-interface-access/idiaaddressmap.md)  
 Umožňuje řídit způsob vypočítá DIA SDK virtuální a relativní virtuální adresy ladění objekty.  
  
 [Idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md)  
 Iniciuje přístup k zdroj symboly ladění.  
  
 [Idiaenumdebugstreamdata –](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)  
 Poskytuje přístup k záznamům v datový proud ladění.  
  
 [Idiaenumdebugstreams –](../../debugger/debug-interface-access/idiaenumdebugstreams.md)  
 Vytvoří výčet různé datové proudy debug obsažené v datovém zdroji.  
  
 [Idiaenumframedata –](../../debugger/debug-interface-access/idiaenumframedata.md)  
 Vytvoří výčet různé datové prvky rámce obsažené v datovém zdroji.  
  
 [Idiaenuminjectedsources –](../../debugger/debug-interface-access/idiaenuminjectedsources.md)  
 Výčet různých vloženého zdrojů obsažené v datovém zdroji.  
  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)  
 Provede výčet různých čísla řádků, které jsou obsažené v datovém zdroji.  
  
 [Idiaenumsectioncontribs –](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)  
 Vytvoří výčet různé části příspěvky obsažené v datovém zdroji.  
  
 [Idiaenumsegments –](../../debugger/debug-interface-access/idiaenumsegments.md)  
 Provede výčet různých segmentů obsažené v datovém zdroji.  
  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)  
 Provede výčet různých zdrojové soubory obsažené v datovém zdroji.  
  
 [Idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md)  
 Provede výčet různých rámce zásobníku, která je k dispozici.  
  
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)  
 Provede výčet různých symboly obsažené v datovém zdroji.  
  
 [Idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)  
 Vytvoří výčet podle adresy různé symboly obsažené v datovém zdroji.  
  
 [Idiaenumtables –](../../debugger/debug-interface-access/idiaenumtables.md)  
 Provede výčet různých tabulky obsažené v datovém zdroji.  
  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)  
 Zpřístupní podrobnosti rámce zásobníku.  
  
 [Idiaimagedata –](../../debugger/debug-interface-access/idiaimagedata.md)  
 Zpřístupní podrobnosti o základní umístění a paměť posunutí modulu nebo image.  
  
 [Idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md)  
 Přístupy zdrojový kód aplikace uložené ve zdroji dat DIA.  
  
 [Idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md)  
 Informace přístupů, které popisuje proces mapování z bloku bajtů image textu číslo řádku zdrojového souboru.  
  
 [Idialoadcallback –](../../debugger/debug-interface-access/idialoadcallback.md)  
 Zpětná volání obdrží z symbol DIA postup vyhledání, čímž umožní uživatelské rozhraní hlásit průběh pokus o umístění.  
  
 [Idialoadcallback2 –](../../debugger/debug-interface-access/idialoadcallback2.md)  
 Zpětná volání obdrží z symbol DIA postup vyhledání, která umožňují omezení uložená vyhledáním proces.  
  
 [Idiapropertystorage –](../../debugger/debug-interface-access/idiapropertystorage.md)  
 Umožňuje číst trvalé vlastnosti sady vlastností DIA.  
  
 [Idiareadexeatrvacallback –](../../debugger/debug-interface-access/idiareadexeatrvacallback.md)  
 Umožňuje aplikaci klienta k poskytování bajtů spustitelného souboru jako zadaný umístěním souboru.  
  
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)  
 Umožňuje aplikaci klienta k poskytování bajtů spustitelný soubor určený relativní virtuální adresu.  
  
 [Idiasectioncontrib –](../../debugger/debug-interface-access/idiasectioncontrib.md)  
 Načte data popisující část příspěvku, tedy blok souvislé paměti přispěli k bitové kopii kompilace.  
  
 [Idiasegment –](../../debugger/debug-interface-access/idiasegment.md)  
 Mapuje dat z číslo oddílu segmenty adresního prostoru.  
  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)  
 Poskytuje kontext dotazu pro symboly ladění.  
  
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)  
 Představuje zdrojového souboru.  
  
 [Idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md)  
 Zpřístupní vlastnosti rámce zásobníku.  
  
 [Idiastackwalker –](../../debugger/debug-interface-access/idiastackwalker.md)  
 Poskytuje možnosti metod protokolů provede pomocí souboru PDB.  
  
 [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md)  
 Udržuje zásobník kontextu mezi volání [idiaframedata::Execute –](../../debugger/debug-interface-access/idiaframedata-execute.md) metoda.  
  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)  
 Usnadňuje procházení zásobníku pomocí souboru databáze (PDB) ladicí program.  
  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)  
 Popisuje vlastnosti instance symbolu.  
  
 [Idiatable –](../../debugger/debug-interface-access/idiatable.md)  
 Vytvoří výčet DIA data zdrojová tabulka.  
  
## <a name="related-sections"></a>Související oddíly  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)  
 Popisuje, výčty a struktury využívané prostředím různé rozhraní DIA SDK.  
  
 [Konstanty (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)  
 Popisuje, k dispozici v sadě DIA SDK konstanty.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)