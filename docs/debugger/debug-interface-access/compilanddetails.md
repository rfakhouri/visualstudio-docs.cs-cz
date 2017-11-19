---
title: "Compilanddetails – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CompilandDetails symbol
ms.assetid: ddc7d794-c622-4c63-b2a6-72f8b2d0022a
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9bfbb1e05dadb18e9357e38d6ed660c248dccec4
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="compilanddetails"></a>CompilandDetails
Informace o kompilace je rozdělená mezi symboly s `SymTagCompiland` značky (nízkou podrobnosti) a `SymTagCompilandDetails` značky (vysokou úroveň podrobností). `SymTagCompilandDetails`vyžaduje, načítání další symboly. Však nabízí širokou řadu informace o kompilace, která není k dispozici `SymTagCompiland` symbol.  
  
## <a name="properties"></a>Vlastnosti  
 V následující tabulce jsou uvedeny vlastnosti, které jsou platné pro tento typ symbolu.  
  
|Vlastnost|Datový typ|Popis|  
|--------------|---------------|-----------------|  
|[Idiasymbol::get_backendbuild –](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|`DWORD`|Číslo sestavení back endu kompilátoru.|  
|[Idiasymbol::get_backendmajor –](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|`DWORD`|Back-end hlavní číslo verze kompilátoru.|  
|[Idiasymbol::get_backendminor –](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|`DWORD`|Číslo podverze back endu kompilátoru.|  
|[Idiasymbol::get_compilername –](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|`BSTR`|Název kompilátoru, která vytváří tento kompilace (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_editandcontinueenabled –](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|`BOOL`|`TRUE`je-li upravit a pokračovat byly povoleny v kompilaci.|  
|[Idiasymbol::get_frontendbuild –](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|`DWORD`|Číslo sestavení front-endu kompilátoru.|  
|[Idiasymbol::get_frontendmajor –](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|`DWORD`|Front-endu hlavní číslo verze kompilátoru.|  
|[Idiasymbol::get_frontendminor –](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|`DWORD`|Počet front-endu podverze kompilátoru.|  
|[Idiasymbol::get_hasdebuginfo –](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|`BOOL`|`TRUE`Pokud tato kompilace má informace o ladění (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_hasmanagedcode –](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|`BOOL`|`TRUE`Pokud tato kompilace obsahuje spravovaný kód (jenom v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_hassecuritychecks –](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|`BOOL`|`TRUE`Pokud kompilace bylo kompilováno s [/GS (Kontrola zabezpečení vyrovnávací paměti)](/cpp/build/reference/gs-buffer-security-check) přepínače kompilátoru (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_iscvtcil –](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|`BOOL`|`TRUE`Pokud kompilace byla převedená z Common mezilehlá jazyk (CIL) kódu do nativního kódu.|  
|[Idiasymbol::get_isdataaligned –](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|`BOOL`|`TRUE`Pokud byl zarovnán uživatelem definované typy (UDT) zadány některé hranic paměti (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_ishotpatchable –](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|`BOOL`|`TRUE`Pokud kompilace bylo kompilováno s [/hotpatch (vytvořit kopii opravitelnou za provozu)](/cpp/build/reference/hotpatch-create-hotpatchable-image) přepínače kompilátoru (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_isltcg –](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|`BOOL`|`TRUE`Pokud kompilace bylo kompilováno s [/ltgc (vytváření kódu v době propojování)](/cpp/build/reference/ltcg-link-time-code-generation) přepínače kompilátoru (pouze v DIA SDK V8.0 nebo novější).|  
|[Idiasymbol::get_ismsilnetmodule –](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|`BOOL`|Hodnota TRUE, pokud kompilace Microsoft Intermediate Language (MSIL) modulu (pouze v v8.0 DIA SDK nebo novější).|  
|[Idiasymbol::get_language –](../../debugger/debug-interface-access/idiasymbol-get-language.md)|`DWORD`|Jazyk zdrojového kódu.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|`IDiaSymbol*`|Symbol pro souboru pro kompilaci.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|`DWORD`|ID nadřazené lexikální symbolu.|  
|[Idiasymbol::get_platform –](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|`DWORD`|Platformy, na kterém byl kompilován souboru pro kompilaci (jeden z [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) hodnoty).|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|`DWORD`|ID indexu symbolu.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|`DWORD`|Vrátí `SymTagCompilandDetails` (jeden z [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnoty).|  
  
## <a name="remarks"></a>Poznámky  
 Kompilátory často jsou dodávány ve formuláři označuje jako dvě průchodu kompilátoru; v některých verzí kompilátoru každém průchodu zpracovává jinou aplikací. Tyto jsou označovány jako kompilátory front-end a back-end, proto vlastnosti symbol čísel verzí back-end a front-endu.  
  
## <a name="see-also"></a>Viz také  
 [Kompilace](../../debugger/debug-interface-access/compiland.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)