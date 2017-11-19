---
title: "Idiasymbol – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol interface
ms.assetid: 01ad328a-736c-4933-a9f8-c2ded19ddd8c
caps.latest.revision: "30"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e4954c691795f71704aab7493ef8df3dbb3f958
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbol"></a>IDiaSymbol
Popisuje vlastnosti instance symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDiaSymbol : IUnknown  
```  
  
## <a name="methods-in-alphabetical-order"></a>Metody v abecedním pořadí  
 Následující tabulka uvádí metody `IDiaSymbol`.  
  
> [!NOTE]
>  Symboly vrátí smysluplných dat pro jenom některé z těchto metod, v závislosti na typu symbolu. Pokud metoda vrátí `S_OK`, pak dané metody vrátila smysluplný data.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md)|Načte všechny podřízené objekty daného symbolu.|  
|[IDiaSymbol::findChildrenEx](../../debugger/debug-interface-access/idiasymbol-findchildrenex.md)|Načte podřízené objekty daného symbolu. Tato metoda je rozšířené verze [idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md).|  
|[IDiaSymbol::findChildrenExByAddr](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyaddr.md)|Načte podřízené objekty daného symbolu, které jsou platné na zadané adrese.|  
|[IDiaSymbol::findChildrenExByRVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyrva.md)|Načte podřízené objekty daného symbolu, které jsou platné v zadaný relativní virtuální adresy (RVA).|  
|[IDiaSymbol::findChildrenExByVA](../../debugger/debug-interface-access/idiasymbol-findchildrenexbyva.md)|Načte podřízené objekty daného symbolu, které jsou platné v zadané virtuální adresy.|  
|[IDiaSymbol::findInlineFramesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyaddr.md)|Načte výčet, který umožňuje klientům k iteraci v rámci celé vložené rámce na danou adresu.|  
|[IDiaSymbol::findInlineFramesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyrva.md)|Načte výčet, který umožňuje klientům k iteraci v rámci celé vložené rámce zadaný relativní virtuální adresy (RVA).|  
|[IDiaSymbol::findInlineFramesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineframesbyva.md)|Načte výčet, který umožňuje klientům k iteraci v rámci celé vložené rámce zadané virtuální adresy (VA).|  
|[IDiaSymbol::findInlineeLines](../../debugger/debug-interface-access/idiasymbol-findinlineelines.md)|Načte výčet, který umožňuje klientům k iteraci v rámci informace číslo řádku všechny funkce, které jsou vložená, přímo nebo nepřímo, v tento symbol.|  
|[IDiaSymbol::findInlineeLinesByAddr](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyaddr.md)|Načte výčet, který umožňuje klientům k iteraci v rámci řádku informace o čísle všech funkcí, které jsou vložená, přímo ani nepřímo, v tento symbol v rámci zadaný rozsah adres.|  
|[IDiaSymbol::findInlineeLinesByRVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyrva.md)|Načte výčet, který umožňuje klientům k iteraci v rámci řádku informace o čísle všech funkcí, které jsou vložená, přímo ani nepřímo, v tento symbol v rámci zadaného relativní virtuální adresy (RVA).|  
|[IDiaSymbol::findInlineeLinesByVA](../../debugger/debug-interface-access/idiasymbol-findinlineelinesbyva.md)|Načte výčet, který umožňuje klientům k iteraci v rámci řádku informace o čísle všech funkcí, které jsou vložená, přímo ani nepřímo, v tento symbol v rámci zadané virtuální adresy (VA).|  
|[IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsbyrvaforacceleratorpointertag.md)|Zadané odpovídající hodnota značky, tato metoda vrátí výčet symboly, které jsou obsaženy v této funkci se zakázaným inzerováním na zadaný relativní virtuální adresu.|  
|[IDiaSymbol::findSymbolsForAcceleratorPointerTag](../../debugger/debug-interface-access/idiasymbol-findsymbolsforacceleratorpointertag.md)|Vrátí počet značek ukazatel akcelerátoru ve funkci se zakázaným inzerováním C++ AMP.|  
|[IDiaSymbol::get_acceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-acceleratorpointertags.md)|Vrátí všechny hodnoty značky ukazatel akcelerátoru, které odpovídají na funkci se zakázaným inzerováním C++ AMP akcelerátoru.|  
|[Idiasymbol::get_access –](../../debugger/debug-interface-access/idiasymbol-get-access.md)|Načte modifikátor přístupu člena třídy.|  
|[Idiasymbol::get_addressoffset –](../../debugger/debug-interface-access/idiasymbol-get-addressoffset.md)|Načte posunutí součástí na adresu umístění.|  
|[Idiasymbol::get_addresssection –](../../debugger/debug-interface-access/idiasymbol-get-addresssection.md)|Načte část oddílu na adresu umístění.|  
|[Idiasymbol::get_addresstaken –](../../debugger/debug-interface-access/idiasymbol-get-addresstaken.md)|Získá příznak označující, zda jiný symbol odkazuje na tuto adresu.|  
|[Idiasymbol::get_age –](../../debugger/debug-interface-access/idiasymbol-get-age.md)|Načte hodnotu stáří databáze programu.|  
|[Idiasymbol::get_arrayindextype –](../../debugger/debug-interface-access/idiasymbol-get-arrayindextype.md)|Načte identifikátor symbol typu index pole.|  
|[Idiasymbol::get_arrayindextypeid –](../../debugger/debug-interface-access/idiasymbol-get-arrayindextypeid.md)|Načte identifikátor pole indexu typ symbolu.|  
|[Idiasymbol::get_backendmajor –](../../debugger/debug-interface-access/idiasymbol-get-backendmajor.md)|Načte back-end hlavní číslo verze.|  
|[Idiasymbol::get_backendminor –](../../debugger/debug-interface-access/idiasymbol-get-backendminor.md)|Načte číslo podverze back-end.|  
|[Idiasymbol::get_backendbuild –](../../debugger/debug-interface-access/idiasymbol-get-backendbuild.md)|Načte číslo sestavení back-end.|  
|[IDiaSymbol::get_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)|Načte posun základní data.|  
|[IDiaSymbol::get_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)|Načte pozici základní data.|  
|[IDiaSymbol::get_baseSymbol](../../debugger/debug-interface-access/idiasymbol-get-basesymbol.md)|Načte symbol, ze kterého je založena ukazatel.|  
|[IDiaSymbol::get_baseSymbolId](../../debugger/debug-interface-access/idiasymbol-get-basesymbolid.md)|Načte ID symbol, ze kterého je založena ukazatel.|  
|[Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)|Načte typ značky jednoduchého typu.|  
|[Idiasymbol::get_bitposition –](../../debugger/debug-interface-access/idiasymbol-get-bitposition.md)|Načte pozici bit umístění.|  
|[IDiaSymbol::get_builtInKind](../../debugger/debug-interface-access/idiasymbol-get-builtinkind.md)|Načte předdefinované druh typu HLSL.|  
|[Idiasymbol::get_callingconvention –](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)|Vrátí konvence volání metody slouží jako ukazatel.|  
|[Idiasymbol::get_classparent –](../../debugger/debug-interface-access/idiasymbol-get-classparent.md)|Získá odkaz na nadřazený Třída symbolu.|  
|[Idiasymbol::get_classparentid –](../../debugger/debug-interface-access/idiasymbol-get-classparentid.md)|Načte identifikátor nadřazené třídy symbolu.|  
|[Idiasymbol::get_code –](../../debugger/debug-interface-access/idiasymbol-get-code.md)|Získá příznak označující, zda je symbol odkazuje na adresu kódu.|  
|[Idiasymbol::get_compilergenerated –](../../debugger/debug-interface-access/idiasymbol-get-compilergenerated.md)|Získá příznak označující, zda je symbol byla generované kompilátorem.|  
|[Idiasymbol::get_compilername –](../../debugger/debug-interface-access/idiasymbol-get-compilername.md)|Načte název kompilátoru použít k vytvoření [kompilace](../../debugger/debug-interface-access/compiland.md).|  
|[Idiasymbol::get_constructor –](../../debugger/debug-interface-access/idiasymbol-get-constructor.md)|Získá příznak označující, zda má uživatelský datový typ konstruktor.|  
|[Idiasymbol::get_container –](../../debugger/debug-interface-access/idiasymbol-get-container.md)|Načte obsahující symbol tento symbol.|  
|[Idiasymbol::get_consttype –](../../debugger/debug-interface-access/idiasymbol-get-consttype.md)|Získá příznak označující, zda je typ uživatelem definované datové konstantní.|  
|[Idiasymbol::get_count –](../../debugger/debug-interface-access/idiasymbol-get-count.md)|Načte počet položek v seznamu nebo pole.|  
|[IDiaSymbol::get_countLiveRanges](../../debugger/debug-interface-access/idiasymbol-get-countliveranges.md)|Načte počet rozsahů platný adres přidružených místní symbolu.|  
|[Idiasymbol::get_customcallingconvention –](../../debugger/debug-interface-access/idiasymbol-get-customcallingconvention.md)|Získá příznak označující, zda funkce, která používá vlastní konvence volání.|  
|[Idiasymbol::get_databytes –](../../debugger/debug-interface-access/idiasymbol-get-databytes.md)|Načte bajtů dat OEM symbolu.|  
|[Idiasymbol::get_datakind –](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)|Načte proměnné klasifikace dat symbolu.|  
|[Idiasymbol::get_editandcontinueenabled –](../../debugger/debug-interface-access/idiasymbol-get-editandcontinueenabled.md)|Načte příznak popisující funkce upravit a pokračovat zkompilovaný program nebo jednotku.|  
|[Idiasymbol::get_farreturn –](../../debugger/debug-interface-access/idiasymbol-get-farreturn.md)|Získá příznak označující, zda funkce používá daleko návratový.|  
|[Idiasymbol::get_frontendmajor –](../../debugger/debug-interface-access/idiasymbol-get-frontendmajor.md)|Načte front-end hlavní číslo verze.|  
|[Idiasymbol::get_frontendminor –](../../debugger/debug-interface-access/idiasymbol-get-frontendminor.md)|Načte číslo front-end podverze.|  
|[Idiasymbol::get_frontendbuild –](../../debugger/debug-interface-access/idiasymbol-get-frontendbuild.md)|Načte číslo front-end sestavení.|  
|[Idiasymbol::get_function –](../../debugger/debug-interface-access/idiasymbol-get-function.md)|Získá příznak označující, zda je veřejný symbol odkazuje na funkci.|  
|[Idiasymbol::get_guid –](../../debugger/debug-interface-access/idiasymbol-get-guid.md)|Načte identifikátor GUID symbolu.|  
|[Idiasymbol::get_hasalloca –](../../debugger/debug-interface-access/idiasymbol-get-hasalloca.md)|Načte příznak označující, zda funkce obsahuje volání `alloca`.|  
|[Idiasymbol::get_hasassignmentoperator –](../../debugger/debug-interface-access/idiasymbol-get-hasassignmentoperator.md)|Získá příznak označující, zda má uživatelský datový typ všechny operátory přiřazení definované.|  
|[Idiasymbol::get_hascastoperator –](../../debugger/debug-interface-access/idiasymbol-get-hascastoperator.md)|Získá příznak označující, zda má uživatelský datový typ všechny operátory přetypování definované.|  
|[Idiasymbol::get_hasdebuginfo –](../../debugger/debug-interface-access/idiasymbol-get-hasdebuginfo.md)|Získá příznak označující, zda kompilace obsahuje všechny informace o ladění.|  
|[Idiasymbol::get_haseh –](../../debugger/debug-interface-access/idiasymbol-get-haseh.md)|Získá příznak označující, zda má funkce obslužnou rutinu výjimky C++ stylu.|  
|[Idiasymbol::get_haseha –](../../debugger/debug-interface-access/idiasymbol-get-haseha.md)|Získá příznak označující, zda má funkce obslužnou rutinu asynchronní výjimky.|  
|[Idiasymbol::get_hasinlasm –](../../debugger/debug-interface-access/idiasymbol-get-hasinlasm.md)|Získá příznak označující, zda má funkce vloženého sestavení.|  
|[Idiasymbol::get_haslongjump –](../../debugger/debug-interface-access/idiasymbol-get-haslongjump.md)|Získá příznak označující, zda funkce obsahuje příkaz longjmp (součást zpracovávání výjimek v jazyce C-style).|  
|[Idiasymbol::get_hasmanagedcode –](../../debugger/debug-interface-access/idiasymbol-get-hasmanagedcode.md)|Získá příznak označující, zda modul obsahuje spravovaného kódu.|  
|[Idiasymbol::get_hasnestedtypes –](../../debugger/debug-interface-access/idiasymbol-get-hasnestedtypes.md)|Získá příznak označující, zda má uživatelský datový typ vnořené definice typů.|  
|[Idiasymbol::get_hassecuritychecks –](../../debugger/debug-interface-access/idiasymbol-get-hassecuritychecks.md)|Načte příznak označující, zda funkce nebo kompilace má kompilovat v kontrol zabezpečení (prostřednictvím [/GS (Kontrola zabezpečení vyrovnávací paměti)](/cpp/build/reference/gs-buffer-security-check) přepínače kompilátoru).|  
|[Idiasymbol::get_hasseh –](../../debugger/debug-interface-access/idiasymbol-get-hasseh.md)|Získá příznak označující, zda má funkce Win32 stylu strukturované zpracování výjimek.|  
|[Idiasymbol::get_hassetjump –](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)|Získá příznak označující, zda obsahuje funkce setjmp příkaz.|  
|[Idiasymbol::get_indirectvirtualbaseclass –](../../debugger/debug-interface-access/idiasymbol-get-indirectvirtualbaseclass.md)|Získá příznak označující, zda je typ uživatelem definované datové nepřímých virtuální základní třídy.|  
|[Idiasymbol::get_inlspec –](../../debugger/debug-interface-access/idiasymbol-get-inlspec.md)|Získá příznak označující, zda funkce byla označena atributem vložené.|  
|[Idiasymbol::get_interruptreturn –](../../debugger/debug-interface-access/idiasymbol-get-interruptreturn.md)|Získá příznak označující, zda má funkce vrátit z přerušení instrukcí.|  
|[Idiasymbol::get_intro –](../../debugger/debug-interface-access/idiasymbol-get-intro.md)|Získá příznak označující, zda funkce virtuální funkce základní třídy.|  
|[IDiaSymbol::get_isAcceleratorGroupSharedLocal](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorgroupsharedlocal.md)|Získá příznak označující, zda je symbol odpovídá skupině sdílené místní proměnné v kódu zkompilovaného pro akcelerátor C++ AMP.|  
|[IDiaSymbol::get_isAcceleratorPointerTagLiveRange](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorpointertagliverange.md)|Načte příznak určující, zda je symbol odpovídá *definice rozsahu symbol* pro komponentu značky v kódu zkompilovaného pro akcelerátor C++ AMP proměnné ukazatele. Definice rozsahu symbol je umístění, proměnné rozsahu adres.|  
|[IDiaSymbol::get_isAcceleratorStubFunction](../../debugger/debug-interface-access/idiasymbol-get-isacceleratorstubfunction.md)|Určuje, zda je symbol odpovídá symbol nejvyšší úrovně funkce pro shaderu zkompilovaném pro akcelerátor, která odpovídá `parallel_for_each` volání.|  
|[Idiasymbol::get_isaggregated –](../../debugger/debug-interface-access/idiasymbol-get-isaggregated.md)|Získá příznak označující, zda data je součástí agregace mnoho symbolů.|  
|[IDiaSymbol::get_isCTypes](../../debugger/debug-interface-access/idiasymbol-get-isctypes.md)|Získá příznak označující, zda soubor symbol obsahuje typy C.|  
|[Idiasymbol::get_iscvtcil –](../../debugger/debug-interface-access/idiasymbol-get-iscvtcil.md)|Získá příznak označující, zda modul byl převeden z Common mezilehlá jazyk (CIL) do nativního kódu.|  
|[Idiasymbol::get_isdataaligned –](../../debugger/debug-interface-access/idiasymbol-get-isdataaligned.md)|Získá příznak označující, zda elementy typu uživatelem definované datové je zarovnán konkrétní hranice.|  
|[IDiaSymbol::get_isHLSLData](../../debugger/debug-interface-access/idiasymbol-get-ishlsldata.md)|Určuje, zda tento symbol představuje data vysokou úroveň shaderu jazyk (HLSL).|  
|[Idiasymbol::get_ishotpatchable –](../../debugger/debug-interface-access/idiasymbol-get-ishotpatchable.md)|Načte příznak označující, zda modul bylo kompilováno s [/hotpatch (vytvořit kopii opravitelnou za provozu)](/cpp/build/reference/hotpatch-create-hotpatchable-image) přepínače kompilátoru.|  
|[Idiasymbol::get_isltcg –](../../debugger/debug-interface-access/idiasymbol-get-isltcg.md)|Získá příznak označující, zda spravované kompilace bylo propojeno s LTCG linkeru.|  
|[IDiaSymbol::get_isMatrixRowMajor](../../debugger/debug-interface-access/idiasymbol-get-ismatrixrowmajor.md)|Určuje, zda matice řádek hlavní.|  
|[Idiasymbol::get_ismsilnetmodule –](../../debugger/debug-interface-access/idiasymbol-get-ismsilnetmodule.md)|Získá příznak označující, zda spravované kompilace .netmodule (obsahující jenom metadata).|  
|[IDiaSymbol::get_isMultipleInheritance](../../debugger/debug-interface-access/idiasymbol-get-ismultipleinheritance.md)|Určuje, zda `this` body ukazatele na člena s vícenásobná dědičnost.|  
|[Idiasymbol::get_isnaked –](../../debugger/debug-interface-access/idiasymbol-get-isnaked.md)|Načte příznak označující, zda má funkce [holé](/cpp/cpp/naked-cpp) atribut.|  
|[IDiaSymbol::get_isOptimizedAway](../../debugger/debug-interface-access/idiasymbol-get-isoptimizedaway.md)|Určuje, zda je proměnná optimalizována rychle.|  
|[IDiaSymbol::get_isPointerBasedOnSymbolValue](../../debugger/debug-interface-access/idiasymbol-get-ispointerbasedonsymbolvalue.md)|Určuje, zda `this` ukazatel je založena na hodnotu symbol.|  
|[IDiaSymbol::get_isPointerToDataMember](../../debugger/debug-interface-access/idiasymbol-get-ispointertodatamember.md)|Určuje, zda tento symbol ukazatele na člena.|  
|[IDiaSymbol::get_isPointerToMemberFunction](../../debugger/debug-interface-access/idiasymbol-get-ispointertomemberfunction.md)|Určuje, zda tento symbol ukazatel na funkci člen.|  
|[IDiaSymbol::get_isReturnValue](../../debugger/debug-interface-access/idiasymbol-get-isreturnvalue.md)|Určuje, zda proměnná představuje návratovou hodnotu.|  
|[IDiaSymbol::get_isSdl](../../debugger/debug-interface-access/idiasymbol-get-issdl.md)|Určuje, jestli je modul kompilovat s parametrem/SDL.|  
|[IDiaSymbol::get_isSingleInheritance](../../debugger/debug-interface-access/idiasymbol-get-issingleinheritance.md)|Určuje, zda `this` body ukazatele na člena s jedna dědičnost.|  
|[Idiasymbol::get_issplitted –](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)|Získá příznak označující, zda data rozdělena do agregace samostatné symbolů.|  
|[Idiasymbol::get_isstatic –](../../debugger/debug-interface-access/idiasymbol-get-isstatic.md)|Získá příznak označující, zda je statický vrstva funkce nebo převodu.|  
|[Idiasymbol::get_isstripped –](../../debugger/debug-interface-access/idiasymbol-get-isstripped.md)|Získá příznak označující, zda mají bylo provedeno oříznutí soukromých symbolů, ze souboru symbol.|  
|[IDiaSymbol::get_isVirtualInheritance](../../debugger/debug-interface-access/idiasymbol-get-isvirtualinheritance.md)|Určuje, zda `this` body ukazatele na člena s virtuální dědičnost.|  
|[Idiasymbol::get_language –](../../debugger/debug-interface-access/idiasymbol-get-language.md)|Získá jazyk zdroje.|  
|[Idiasymbol::get_length –](../../debugger/debug-interface-access/idiasymbol-get-length.md)|Získá počet bajtů paměti, které objekt reprezentovaný rozhraním tento symbol.|  
|[Idiasymbol::get_lexicalparent –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparent.md)|Získá odkaz na nadřazený lexikální symbolu.|  
|[Idiasymbol::get_lexicalparentid –](../../debugger/debug-interface-access/idiasymbol-get-lexicalparentid.md)|Načte identifikátor lexikální nadřazené symbolu.|  
|[Idiasymbol::get_libraryname –](../../debugger/debug-interface-access/idiasymbol-get-libraryname.md)|Načte název souboru souboru knihovny nebo objekt, ze kterého se načetl objekt.|  
|[IDiaSymbol::get_liveRangeLength](../../debugger/debug-interface-access/idiasymbol-get-liverangelength.md)|Vrátí délku rozsah adres, ve kterém je platný místní symbolu.|  
|[IDiaSymbol::get_liveRangeStartAddressSection](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddresssection.md)|Vrátí část oddílu počáteční rozsah adres, ve kterém je platný místní symbolu.|  
|[IDiaSymbol::get_liveRangeStartAddressOffset](../../debugger/debug-interface-access/idiasymbol-get-liverangestartaddressoffset.md)|Vrátí posunutí část počáteční rozsah adres, ve kterém je platný místní symbolu.|  
|[IDiaSymbol::get_liveRangeStartRelativeVirtualAddress](../../debugger/debug-interface-access/idiasymbol-get-liverangestartrelativevirtualaddress.md)|Vrátí začátek rozsahu adres, ve kterém je platný místní symbolu.|  
|[Idiasymbol::get_locationtype –](../../debugger/debug-interface-access/idiasymbol-get-locationtype.md)|Načte typ umístění symbolu data.|  
|[Idiasymbol::get_lowerbound –](../../debugger/debug-interface-access/idiasymbol-get-lowerbound.md)|Načte dolní hranice FORTRAN pole dimenze.|  
|[Idiasymbol::get_lowerboundid –](../../debugger/debug-interface-access/idiasymbol-get-lowerboundid.md)|Načte identifikátor symbol dolní hranice FORTRAN pole dimenze.|  
|[Idiasymbol::get_machinetype –](../../debugger/debug-interface-access/idiasymbol-get-machinetype.md)|Načte typ cíle procesoru.|  
|[Idiasymbol::get_managed –](../../debugger/debug-interface-access/idiasymbol-get-managed.md)|Načte příznak, která určuje, zda je symbol odkazuje na spravovaný kód.|  
|[IDiaSymbol::get_memorySpaceKind](../../debugger/debug-interface-access/idiasymbol-get-memoryspacekind.md)|Načte druh místo paměti.|  
|[Idiasymbol::get_msil –](../../debugger/debug-interface-access/idiasymbol-get-msil.md)|Získá příznak označující, zda je symbol odkazuje na kód Microsoft Intermediate Language (MSIL).|  
|[Idiasymbol::get_Name –](../../debugger/debug-interface-access/idiasymbol-get-name.md)|Načte název symbolu.|  
|[Idiasymbol::get_nested –](../../debugger/debug-interface-access/idiasymbol-get-nested.md)|Získá příznak označující, zda je uživatelský datový typ vnořený.|  
|[Idiasymbol::get_noinline –](../../debugger/debug-interface-access/idiasymbol-get-noinline.md)|Načte příznak označující, zda je označené jako funkci [noinline](/cpp/cpp/noinline) atribut.|  
|[Idiasymbol::get_noreturn –](../../debugger/debug-interface-access/idiasymbol-get-noreturn.md)|Načte příznak označující, zda bylo deklarováno funkce s [noreturn](/cpp/cpp/noreturn) atribut.|  
|[Idiasymbol::get_nostackordering –](../../debugger/debug-interface-access/idiasymbol-get-nostackordering.md)|Získá příznak označující, zda žádná zásobníku řazení může provést v rámci zásobníku kontrola vyrovnávací paměti.|  
|[Idiasymbol::get_notreached –](../../debugger/debug-interface-access/idiasymbol-get-notreached.md)|Získá příznak označující, zda funkce nebo popisek není přístupný.|  
|[IDiaSymbol::get_numberOfAcceleratorPointerTags](../../debugger/debug-interface-access/idiasymbol-get-numberofacceleratorpointertags.md)|Vrátí počet značek ukazatel akcelerátoru ve funkci se zakázaným inzerováním C++ AMP.|  
|[IDiaSymbol::get_numberOfModifiers](../../debugger/debug-interface-access/idiasymbol-get-numberofmodifiers.md)|Načte počet modifikátory, které se použijí pro původní typ.|  
|[IDiaSymbol::get_numberOfRegisterIndices](../../debugger/debug-interface-access/idiasymbol-get-numberofregisterindices.md)|Načte počet indexů registrace.|  
|[IDiaSymbol::get_numberOfRows](../../debugger/debug-interface-access/idiasymbol-get-numberofrows.md)|Získá počet řádků v matici.|  
|[IDiaSymbol::get_numberOfColumns](../../debugger/debug-interface-access/idiasymbol-get-numberofcolumns.md)|Načte počet sloupců v matici.|  
|[IDiaSymbol::get_objectFileName](../../debugger/debug-interface-access/idiasymbol-get-objectfilename.md)|Načte název souboru objektů.|  
|[Idiasymbol::get_objectpointertype –](../../debugger/debug-interface-access/idiasymbol-get-objectpointertype.md)|Načte typ ukazatele objektu pro metodu třídy.|  
|[Idiasymbol::get_oemid –](../../debugger/debug-interface-access/idiasymbol-get-oemid.md)|Načte symbolu `oemId` hodnotu.|  
|[Idiasymbol::get_oemsymbolid –](../../debugger/debug-interface-access/idiasymbol-get-oemsymbolid.md)|Načte symbolu `oemSymbolId` hodnotu.|  
|[Idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md)|Načte posun umístění symbolu.|  
|[Idiasymbol::get_optimizedcodedebuginfo –](../../debugger/debug-interface-access/idiasymbol-get-optimizedcodedebuginfo.md)|Načte příznak označující, zda funkce nebo popisek obsahuje optimalizovaný kód také jako informace o ladění.|  
|[Idiasymbol::get_overloadedoperator –](../../debugger/debug-interface-access/idiasymbol-get-overloadedoperator.md)|Získá příznak označující, zda má uživatelský datový typ přetížený operátory.|  
|[Idiasymbol::get_packed –](../../debugger/debug-interface-access/idiasymbol-get-packed.md)|Získá příznak označující, zda je uživatelský datový typ zabalena.|  
|[Idiasymbol::get_platform –](../../debugger/debug-interface-access/idiasymbol-get-platform.md)|Načte typ platformy, pro které byl zpracován program nebo kompilace.|  
|[Idiasymbol::get_pure –](../../debugger/debug-interface-access/idiasymbol-get-pure.md)|Načte příznak této určující, zda je funkce čistý virtuální.|  
|[Idiasymbol::get_rank –](../../debugger/debug-interface-access/idiasymbol-get-rank.md)|Načte pořadí FORTRAN multidimenzionálního pole.|  
|[Idiasymbol::get_reference –](../../debugger/debug-interface-access/idiasymbol-get-reference.md)|Načte příznak určující, zda je ukazatel typu odkaz.|  
|[Idiasymbol::get_registerid –](../../debugger/debug-interface-access/idiasymbol-get-registerid.md)|Načte označení registrace umístění.|  
|[IDiaSymbol::get_registerType](../../debugger/debug-interface-access/idiasymbol-get-registertype.md)|Načte typ zaregistrovat.|  
|[Idiasymbol::get_relativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-relativevirtualaddress.md)|Načte relativní virtuální adresy (RVA) umístění.|  
|[IDiaSymbol::get_restrictedType](../../debugger/debug-interface-access/idiasymbol-get-restrictedtype.md)|Určuje, zda `this` ukazatel je označený jako s omezeným přístupem.|  
|[IDiaSymbol::get_samplerSlot](../../debugger/debug-interface-access/idiasymbol-get-samplerslot.md)|Načte sampler slot.|  
|[Idiasymbol::get_scoped –](../../debugger/debug-interface-access/idiasymbol-get-scoped.md)|Získá příznak označující, zda uživatelský datový typ se zobrazí v neglobální lexikální oboru.|  
|[Idiasymbol::get_signature –](../../debugger/debug-interface-access/idiasymbol-get-signature.md)|Načte hodnotu podpis symbolu.|  
|[IDiaSymbol::get_sizeInUdt](../../debugger/debug-interface-access/idiasymbol-get-sizeinudt.md)|Získá velikost člena typu definovaný uživatelem.|  
|[Idiasymbol::get_slot –](../../debugger/debug-interface-access/idiasymbol-get-slot.md)|Načte číslo pozice umístění.|  
|[Idiasymbol::get_sourcefilename –](../../debugger/debug-interface-access/idiasymbol-get-sourcefilename.md)|Načte název souboru zdrojového souboru.|  
|[IDiaSymbol::getSrcLineOnTypeDefn](../../debugger/debug-interface-access/idiasymbol-getsrclineontypedefn.md)|Načte zdrojového souboru a řádku číslo, které označuje, kde je definován na zadaný typ definovaný uživatelem.|  
|[IDiaSymbol::get_stride](../../debugger/debug-interface-access/idiasymbol-get-stride.md)|Načte stride matice nebo strided pole.|  
|[IDiaSymbol::get_subType](../../debugger/debug-interface-access/idiasymbol-get-subtype.md)|Načte typ sub.|  
|[IDiaSymbol::get_subTypeId](../../debugger/debug-interface-access/idiasymbol-get-subtypeid.md)|Načte ID dílčí typu.|  
|[Idiasymbol::get_symbolsfilename –](../../debugger/debug-interface-access/idiasymbol-get-symbolsfilename.md)|Načte název souboru, ze které byla načtena symboly.|  
|[Idiasymbol::get_symindexid –](../../debugger/debug-interface-access/idiasymbol-get-symindexid.md)|Načte identifikátor jedinečný symbol.|  
|[Idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md)|Načte třídění typ symbolu.|  
|[Idiasymbol::get_targetoffset –](../../debugger/debug-interface-access/idiasymbol-get-targetoffset.md)|Načte části Posunutí převodu cíle.|  
|[Idiasymbol::get_targetrelativevirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-targetrelativevirtualaddress.md)|Načte relativní virtuální adresy (RVA) převodu cíl.|  
|[Idiasymbol::get_targetsection –](../../debugger/debug-interface-access/idiasymbol-get-targetsection.md)|Načte oddíl adresy převodu cíle.|  
|[Idiasymbol::get_targetvirtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-targetvirtualaddress.md)|Načte virtuální adresy (VA) převodu cíle.|  
|[IDiaSymbol::get_textureSlot](../../debugger/debug-interface-access/idiasymbol-get-textureslot.md)|Načte texture slot.|  
|[Idiasymbol::get_thisadjust –](../../debugger/debug-interface-access/idiasymbol-get-thisadjust.md)|Načte logické `this` likvidátor pro metodu.|  
|[Idiasymbol::get_thunkordinal –](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)|Načte typ převodu funkce.|  
|[Idiasymbol::get_timestamp –](../../debugger/debug-interface-access/idiasymbol-get-timestamp.md)|Načte časové razítko základní spustitelného souboru.|  
|[Idiasymbol::get_token –](../../debugger/debug-interface-access/idiasymbol-get-token.md)|Načte metadata tokenu spravované funkce nebo proměnná.|  
|[Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)|Získá odkaz na podpis funkce.|  
|[Idiasymbol::get_typeid –](../../debugger/debug-interface-access/idiasymbol-get-typeid.md)|Načte identifikátor typ symbolu.|  
|[Idiasymbol::get_types –](../../debugger/debug-interface-access/idiasymbol-get-types.md)|Načte pole hodnot typu kompilátoru specifické pro tento symbol.|  
|[Idiasymbol::get_typeids –](../../debugger/debug-interface-access/idiasymbol-get-typeids.md)|Načte pole hodnot typu kompilátoru konkrétní identifikátor pro tento symbol.|  
|[IDiaSymbol::get_uavSlot](../../debugger/debug-interface-access/idiasymbol-get-uavslot.md)|Načte pozici bezpilotní letadla.|  
|[Idiasymbol::get_udtkind –](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)|Načte řadu uživatelem definovaný typ (UDT).|  
|[Idiasymbol::get_unalignedtype –](../../debugger/debug-interface-access/idiasymbol-get-unalignedtype.md)|Získá příznak označující, zda je typ uživatelem definované datové nezarovnané.|  
|[Idiasymbol::get_undecoratedname –](../../debugger/debug-interface-access/idiasymbol-get-undecoratedname.md)|Načte název bez upraveného pro C++ dekorované, nebo propojení, název.|  
|[Idiasymbol::get_undecoratednameex –](../../debugger/debug-interface-access/idiasymbol-get-undecoratednameex.md)|Rozšíření `get_undecoratedName` metoda, která načte bez upraveného název založená na hodnotě pole rozšíření.|  
|[IDiaSymbol::get_unmodifiedTypeId](../../debugger/debug-interface-access/idiasymbol-get-unmodifiedtypeid.md)|Načte ID typu původní (beze změny).|  
|[Idiasymbol::get_upperbound –](../../debugger/debug-interface-access/idiasymbol-get-upperbound.md)|Načte horní mez dimenzi FORTRAN pole.|  
|[Idiasymbol::get_upperboundid –](../../debugger/debug-interface-access/idiasymbol-get-upperboundid.md)|Načte identifikátor symbol horní mez dimenzi FORTRAN pole.|  
|[Idiasymbol::get_value –](../../debugger/debug-interface-access/idiasymbol-get-value.md)|Načte hodnotu konstanty.|  
|[Idiasymbol::get_virtual –](../../debugger/debug-interface-access/idiasymbol-get-virtual.md)|Načte příznak určující, zda je virtuální funkce.|  
|[Idiasymbol::get_virtualaddress –](../../debugger/debug-interface-access/idiasymbol-get-virtualaddress.md)|Načte virtuální adresy (VA) umístění.|  
|[Idiasymbol::get_virtualbaseclass –](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseclass.md)|Získá příznak označující, zda je typ uživatelem definované datové virtuální základní třídy.|  
|[Idiasymbol::get_virtualbasedispindex –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasedispindex.md)|Načte index pro tabulku virtuální základní posunutí.|  
|[Idiasymbol::get_virtualbaseoffset –](../../debugger/debug-interface-access/idiasymbol-get-virtualbaseoffset.md)|Načte posun v tabulce virtuální funkce virtuální funkce.|  
|[Idiasymbol::get_virtualbasepointeroffset –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasepointeroffset.md)|Načte posun virtuální základní ukazatele.|  
|[Idiasymbol::get_virtualbasetabletype –](../../debugger/debug-interface-access/idiasymbol-get-virtualbasetabletype.md)|Načte typ ukazatele virtuální základní tabulky.|  
|[Idiasymbol::get_virtualtableshape –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshape.md)|Načte rozhraní symbol typu virtuální pro uživatelem definovaný typ tabulky.|  
|[Idiasymbol::get_virtualtableshapeid –](../../debugger/debug-interface-access/idiasymbol-get-virtualtableshapeid.md)|Načte identifikátor virtuální tabulku tvar symbolu.|  
|[Idiasymbol::get_volatiletype –](../../debugger/debug-interface-access/idiasymbol-get-volatiletype.md)|Získá příznak označující, zda je typ uživatelem definované datové volatile.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Získejte toto rozhraní volání jedné z následujících metod:  
  
-   [Idiaenumsymbols::Item –](../../debugger/debug-interface-access/idiaenumsymbols-item.md)  
  
-   [Idiaenumsymbols::Next –](../../debugger/debug-interface-access/idiaenumsymbols-next.md)  
  
-   [Idiaenumsymbolsbyaddr::Next –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-next.md)  
  
-   [Idiaenumsymbolsbyaddr::prev –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-prev.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyaddr.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyrva –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyrva.md)  
  
-   [Idiaenumsymbolsbyaddr::symbolbyva –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)  
  
-   [Idiasession::findsymbolbyaddr –](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [Idiasession::findsymbolbyrva –](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [Idiasession::findsymbolbyrvaex –](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [Idiasession::findsymbolbyva –](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [Idiasession::findsymbolbyvaex –](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [Idiasession::findsymbolbytoken –](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [Idiasession::symbolbyid –](../../debugger/debug-interface-access/idiasession-symbolbyid.md)  
  
-   [Idiastackwalkhelper::symbolforva –](../../debugger/debug-interface-access/idiastackwalkhelper-symbolforva.md)  
  
-   [Idiasymbol::get_types –](../../debugger/debug-interface-access/idiasymbol-get-types.md)  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak zobrazit místní proměnné pro funkci v dané relativní virtuální adresu. Také ukazuje, jak symboly různé typy jsou vzájemně souvisí.  
  
> [!NOTE]
>  `CDiaBSTR`je třída, která zabalí `BSTR` a automaticky zpracovává uvolnění řetězec při vytváření instance ocitne mimo rozsah.  
  
```C++  
void DumpLocalVars( DWORD rva, IDiaSession *pSession )  
{  
    CComPtr< IDiaSymbol > pBlock;  
    if ( FAILED( psession->findSymbolByRVA( rva, SymTagBlock, &pBlock ) ) )  
    {  
        Fatal( "Failed to find symbols by RVA" );  
    }  
    CComPtr< IDiaSymbol > pscope;  
    for ( ; pBlock != NULL; )  
    {  
        CComPtr< IDiaEnumSymbols > pEnum;  
        // local data search  
        if ( FAILED( pBlock->findChildren( SymTagNull, NULL, nsNone, &pEnum ) ) )  
        {  
            Fatal( "Local scope findChildren failed" );  
        }  
        CComPtr< IDiaSymbol > pSymbol;  
        DWORD tag;  
        DWORD celt;  
        while ( pEnum != NULL &&  
                SUCCEEDED( pEnum->Next( 1, &pSymbol, &celt ) ) &&  
                celt == 1)  
        {  
            pSymbol->get_symTag( &tag );  
            if ( tag == SymTagData )  
            {  
                CDiaBSTR name;  
                DWORD    kind;  
                pSymbol->get_name( &name );  
                pSymbol->get_dataKind( &kind );  
                if ( name != NULL )  
                    wprintf_s( L"\t%s (%s)\n", name, szDataKinds[ kind ] );  
            }  
            else if ( tag == SymTagAnnotation )  
            {  
                CComPtr< IDiaEnumSymbols > pValues;  
                // local data search  
                wprintf_s( L"\tAnnotation:\n" );  
                if ( FAILED( pSymbol->findChildren( SymTagNull, NULL, nsNone, &pValues ) ) )  
                    Fatal( "Annotation findChildren failed" );  
                pSymbol = NULL;  
                while ( pValues != NULL &&  
                        SUCCEEDED( pValues->Next( 1, &pSymbol, &celt ) ) &&  
                        celt == 1 )  
                {  
                    CComVariant value;  
                    if ( pSymbol->get_value( &value ) != S_OK )  
                        Fatal( "No value for annotation data." );  
                    wprintf_s( L"\t\t%ws\n", value.bstrVal );  
                    pSymbol = NULL;  
                }  
            }  
            pSymbol = NULL;  
        }  
        pBlock->get_symTag( &tag );   
        if ( tag == SymTagFunction )    // stop when at function scope  
            break;  
        // move to lexical parent  
        CComPtr< IDiaSymbol > pParent;  
        if ( SUCCEEDED( pBlock->get_lexicalParent( &pParent ) )  
            && pParent != NULL ) {  
            pBlock = pParent;  
        }  
        else  
        {  
            Fatal( "Finding lexical parent failed." );  
        }  
    };  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 `Header:`Dia2.h  
  
 Knihovna: diaguids.lib  
  
 Knihovny DLL: msdia80.dll  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní (přístup k rozhraní SDK ladění)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [Idiaenumsymbolsbyaddr –](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [Idiaenumsymbols –](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Hierarchie tříd typů symbolů](../../debugger/debug-interface-access/class-hierarchy-of-symbol-types.md)   
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)   
 [Kompilace](../../debugger/debug-interface-access/compiland.md)