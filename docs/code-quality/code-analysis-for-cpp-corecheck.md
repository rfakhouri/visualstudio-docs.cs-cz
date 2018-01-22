---
title: "Visual Studio C++ základní pokyny kontrolu odkaz | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: code analysis, C++ core check
ms.assetid: f1429463-136e-41ed-8a75-a8dbf0b4fd89
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d5db13aa350e33a297981066f36c3d1dfd1ecb67
ms.sourcegitcommit: bd16e764134c436d2d2f46490f51234d5246ee50
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/22/2018
---
# <a name="c-core-guidelines-checker-reference"></a>C++ základní pokyny pro kontrolu odkaz
Tato část uvádí C++ základní pokyny pro kontrolu upozornění. Informace o analýze kódu najdete v tématu [/ analyze (Analýza kódu)](/cpp/build/reference/analyze-code-analysis) a [rychlé zahájení: Analýza kódu pro C/C++](../code-quality/quick-start-code-analysis-for-c-cpp.md).  
  
**Poznámka:**: upozornění patřit do více než jedné skupiny, a ne všechny upozornění mít referenční téma.

## <a name="ownerpointer-group"></a>OWNER_POINTER skupiny

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)  
  Vrátí objekt oboru místo přidělené haldy, pokud má konstruktor move. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr). 
     
[C26403 RESET_OR_DELETE_OWNER](C26403.md)  
  Resetovat nebo explicitně odstranit vlastníka\<T > ukazatel % variable %. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  
     
[C26404 DONT_DELETE_INVALID](C26404.md)  
  Neodstraňujte vlastníka\<T >, může být v neplatném stavu. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  

[C26405 DONT_ASSIGN_TO_VALID](C26405.md)  
  Nepřiřazujte vlastníka\<T >, může být v platném stavu. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  

[C26406 DONT_ASSIGN_RAW_TO_OWNER](C26406.md)  
  Nepřiřazujte nezpracovaná ukazatel na vlastníka\<T >. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr).  
  
[C26407 DONT_HEAP_ALLOCATE_UNNECESSARILY](C26407.md)  
  Dáváte přednost vymezená objekty, nemusíte-přidělení haldy zbytečně. V tématu [C++ základní pokyny R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  

[C26429 USE_NOTNULL](C26429.md)  
  Symbol '% symbol %, je vůbec neotestovali pro nullness, může být označen jako not_null. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  

[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  Symbol 'symbol %' není otestovaná na nullness u všech cest. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  Typ výrazu '% expr %' je již gsl::not_null. Neprovádějte testování ho pro nullness. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  

## <a name="rawpointer-group"></a>RAW_POINTER skupiny
 
[C26400  NO_RAW_POINTER_ASSIGNMENT](c26400.md)  
Nepřiřazujte výsledek přidělení nebo volání funkce s vlastníkem\<T > vrátí hodnotu k nezpracované ukazatel, pomocí vlastníka\<T > místo toho. V tématu [C++ základní pokyny I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw). 

[C26401 DONT_DELETE_NON_OWNER](c26401.md)  
Neodstraňujte nezpracovaná ukazatele, který není vlastníkem\<T >. V tématu [C++ základní pokyny I.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Ri-raw). 

[C26402 DONT_HEAP_ALLOCATE_MOVABLE_RESULT](C26402.md)   vrátí objekt oboru místo přidělené haldy, pokud má konstruktor move. V tématu [C++ základní pokyny R.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-ptr). 
 
[C26408 NO_MALLOC_FREE](C26408.md)  
  Vyhněte se malloc() a free(), raději nothrow verze nové s odstranit. V tématu [C++ základní pokyny R.10](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-mallocfree).  
  
[C26409 NO_NEW_DELETE](C26409.md)  
  Vyhněte se volání nové a explicitně odstranit, použijte std::make_unique\<T > místo toho. V tématu [C++ základní pokyny R.11](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-newdelete).  

[C26429 USE_NOTNULL](C26429.md)  
  Symbol '% symbol %, je vůbec neotestovali pro nullness, může být označen jako not_null. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26430 TEST_ON_ALL_PATHS](C26430.md)  
  Symbol 'symbol %' není otestovaná na nullness u všech cest. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26431 DONT_TEST_NOTNULL](C26431.md)  
  Typ výrazu '% expr %' je již gsl::not_null. Neprovádějte testování ho pro nullness. V tématu [C++ základní pokyny F.23](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f23-use-a-not_nullt-to-indicate-that-null-is-not-a-valid-value).  
  
[C26481 NO_POINTER_ARITHMETIC](C26481.md)  
  Nepoužívejte aritmetika ukazatele. Místo toho použijte rozpětí. V tématu [C++ základní pokyny Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  Výraz '% expr %': žádná pole pro decay ukazatel. V tématu [C++ základní pokyny Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

## <a name="uniquepointer-group"></a>UNIQUE_POINTER skupiny
  
[C26410 NO_REF_TO_CONST_UNIQUE_PTR](C26410.md)  
  Parametr % parametr %, je odkaz na `const` jedinečný ukazatele, použijte const T * nebo const T & místo. V tématu [C++ základní pokyny R.32](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-uniqueptrparam).  
     
[C26411 NO_REF_TO_UNIQUE_PTR](C26411.md)  
  Parametr % parametr %, je odkaz na ukazatel jedinečný a není přeřazena ani resetovat, používat T * nebo T & místo. V tématu [C++ základní pokyny R.33](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-reseat).  
     
[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  Přesunout, kopírovat, přiřazení nebo resetovat místní inteligentní ukazatel "% symbol". V tématu [C++ základní pokyny R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  Chytré ukazatele parametr '% symbol %, se používají pouze pro přístup obsažené ukazatele. Použít T * nebo T & místo. V tématu [C++ základní pokyny R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).  

## <a name="sharedpointer-group"></a>SHARED_POINTER skupiny

[C26414 RESET_LOCAL_SMART_PTR](C26414.md)  
  Přesunout, kopírovat, přiřazení nebo resetovat místní inteligentní ukazatel "% symbol". V tématu [C++ základní pokyny R.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-scoped).  
    
[C26415 SMART_PTR_NOT_NEEDED](C26415.md)  
  Chytré ukazatele parametr '% symbol %, se používají pouze pro přístup obsažené ukazatele. Použít T * nebo T & místo. V tématu [C++ základní pokyny R.30](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-smartptrparam).  
    
[C26416 NO_RVALUE_REF_SHARED_PTR](C26416.md)  
  Parametr sdílené ukazatel % symbol %, je předaná deklarátor odkazu. Předání hodnotou místo. V tématu [C++ základní pokyny R.34](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-owner).  
  
[C26417 NO_LVALUE_REF_SHARED_PTR](C26417.md)  
  Parametr sdílené ukazatel % symbol %, je předaná odkaz a neprovádí vynulování nebo znovu přiřazen. Použít T * nebo T & místo. V tématu [C++ základní pokyny R.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam).  
  
[C26418 NO_VALUE_OR_CONST_REF_SHARED_PTR](C26418.md)  
  Parametr sdílené ukazatel % symbol %, není zkopírovat nebo přesunout. Použít T * nebo T & místo. V tématu [C++ základní pokyny R.36](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rr-sharedptrparam-const).  

## <a name="declaration-group"></a>DEKLARACE skupiny
    
[C26426 NO_GLOBAL_INIT_CALLS](C26426.md)  
  Globální inicializátoru volá bez constexpr funkce "% symbol". V tématu [C++ základní pokyny I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).  
  
[C26427 NO_GLOBAL_INIT_EXTERNS](C26427.md)  
  Globální inicializátoru objektu extern % symbol %, má přístup k. V tématu [C++ základní pokyny I.22](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#i22-avoid-complex-initialization-of-global-objects).  
  
[C26444 NO_UNNAMED_RAII_OBJECTS](c26444.md) nepoužívejte nepojmenované objekty s vlastní vytváření a odstraňování. [ES.84: (Nedoporučujeme) deklarovat místní proměnné bez názvu](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).

## <a name="class-group"></a>Skupina – třída
    
[C26432 DEFINE_OR_DELETE_SPECIAL_OPS](C26432.md)  
  Pokud definovat nebo odstranit všechny operace výchozí typ '% symbol %', definovat nebo odstraňte všechny. V tématu [C++ základní pokyny C.21](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c21-if-you-define-or-delete-any-default-operation-define-or-delete-them-all).  


[C26433 OVERRIDE_EXPLICITLY](c26433.md) funkce 'symbol %' by měl být označen 'override'. V tématu [ C.128: virtuální funkce by měl určovat právě jeden virtuální, mají přednost před, nebo konečné](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final). 

  
[C26434 DONT_HIDE_METHODS](C26434.md)  
  Funkce '% symbol_1 %' skryje bez virtuální funkce '% symbol_2 %'. V tématu [C++ základní pokyny C.128](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c128-virtual-functions-should-specify-exactly-one-of-virtual-override-or-final).  
  

[C26435 SINGLE_VIRTUAL_SPECIFICATION](c26435.md) funkce 'symbol %' by měl určovat právě jeden z 'virtuální', 'přepsat' nebo 'konečné'. V tématu [ C.128: virtuální funkce by měl určovat právě jeden virtuální, mají přednost před, nebo konečné](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md). 


[C26436 NEED_VIRTUAL_DTOR](C26436.md)  
  Typ '% symbol %' s virtuální funkcí musí buď veřejné virtuální nebo chráněného nevirtuální destruktor. V tématu [C++ základní pokyny C.35](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#c35-a-base-class-destructor-should-be-either-public-and-virtual-or-protected-and-nonvirtual).  


[C26443 NO_EXPLICIT_DTOR_OVERRIDE](c26443.md) přepíše destruktor neměli používat explicitní 'override' nebo 'virtuální' specifikátory. V tématu [C.128: virtuální funkce by měl určovat právě jeden virtuální, mají přednost před, nebo konečné](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md).


## <a name="type-group"></a>Typ skupiny
    
[C26437 DONT_SLICE](C26437.md)  
  Není řezu. V tématu [C++ základní pokyny ES.63](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es63-dont-slice).  

## <a name="style-group"></a>Styl skupiny  
[C26438 NO_GOTO](C26438.md)  
  Vyhněte se `goto`. V tématu [C++ základní pokyny ES.76](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es76-avoid-goto).  
  
## <a name="function-group"></a>Funkce skupiny
    
[C26439 SPECIAL_NOEXCEPT](C26439.md)  
  Tento druh – funkce nemusí výjimku. Deklarujte ji `noexcept`. V tématu [C++ základní pokyny F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).  
  
[C26440 DECLARE_NOEXCEPT](C26440.md)  
  Funkce 'symbol %' lze deklarovat `noexcept`. V tématu [C++ základní pokyny F.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#f6-if-your-function-may-not-throw-declare-it-noexcept).  

## <a name="concurrency-group"></a>Skupiny SOUBĚŽNOSTI
    
[C26441 NO_UNNAMED_GUARDS](C26441.md)  
 Ochrana objekty musí mít název. V tématu [C++ základní pokyny cp.44](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#cp44-remember-to-name-your-lock_guards-and-unique_locks).  

## <a name="const-group"></a>CONST skupiny
    
C26460 USE_CONST_REFERENCE_ARGUMENTS  
  Argument odkaz '% argument %' pro funkci '% funkce %, může být označen jako `const`. V tématu [C++ základní pokyny con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).  
  
C26461 USE_CONST_POINTER_ARGUMENTS: argument ukazatel '% argument %' pro funkci '% funkce %, může být označen jako ukazatel na `const`. V tématu [C++ základní pokyny con.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-ref).  
  
C26462 USE_CONST_POINTER_FOR_VARIABLE  
  Hodnota ukazuje % variable % je přiřadit pouze jednou, označte ji jako ukazatel na `const`. V tématu [C++ základní pokyny con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26463 USE_CONST_FOR_ELEMENTS  
  Elementy pole % pole %, jsou přiřazeny pouze jednou, označit elementy `const`. V tématu [C++ základní pokyny con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26464 USE_CONST_POINTER_FOR_ELEMENTS  
  Hodnoty ukazující na elementy pole % pole %, jsou přiřazeny pouze jednou, elementy označit jako ukazatel na `const`. V tématu [C++ základní pokyny con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  

C26496 USE_CONST_FOR_VARIABLE  
  Proměnná % variable % je přiřadit pouze jednou, označte ji jako `const`. V tématu [C++ základní pokyny con.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#con4-use-const-to-define-objects-with-values-that-do-not-change-after-construction).  
  
C26497 USE_CONSTEXPR_FOR_FUNCTION  
  Tato funkce funkce % může být označen `constexpr` Pokud se požaduje vyhodnocení kompilaci. V tématu [C++ základní pokyny F.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rf-constexpr).  
  
C26498 USE_CONSTEXPR_FOR_FUNCTIONCALL  
  Pomocí této funkce % volání funkce % `constexpr` Pokud se požaduje vyhodnocení kompilaci. V tématu [C++ základní pokyny con.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Rconst-constexpr).  

## <a name="type-group"></a>Typ skupiny
C26465 NO_CONST_CAST_UNNECESSARY  
  Nepoužívejte `const_cast` přetypovat rychle `const`. `const_cast`není vyžadována. constness nebo volatility není odebírán tento převod. V tématu [C++ základní pokyny Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-constcast).  
  
C26466 NO_STATIC_DOWNCAST_POLYMORPHIC  
  Nepoužívejte `static_cast` downcasts. Přetypování z polymorfní typ měli používat dynamic_cast. V tématu [C++ základní pokyny Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-downcast).  
  
C26471 NO_REINTERPRET_CAST_FROM_VOID_PTR  
  Nepoužívejte `reinterpret_cast`. Můžete použít přetypování z void * `static_cast`. V tématu [C++ základní pokyny Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26472 NO_CASTS_FOR_ARITHMETIC_CONVERSION](C26472.md)  
  Nepoužívejte `static_cast` pro aritmetické převody. Použít inicializace složené závorce, gsl::narrow_cast nebo gsl::narow. V tématu [C++ základní pokyny Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26473 NO_IDENTITY_CAST](C26473.md)  
  Nemáte přetypování mezi typy ukazatelů, kde typ zdrojový a cílový typ identická. V tématu [C++ základní pokyny Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26474 NO_IMPLICIT_CAST](C26474.md)  
  Mezi typy ukazatelů při převodu může být implicitní nemáte přetypování. V tématu [C++ základní pokyny Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#Pro-type-reinterpretcast).  
  
[C26475 NO_FUNCTION_STYLE_CASTS](C26475.md)  
  Nepoužívejte styl funkce C-přetypování. V tématu [C++ základní pokyny ES.49](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#es49-if-you-must-use-a-cast-use-a-named-cast).  
     
C26490 NO_REINTERPRET_CAST  
  Nepoužívejte `reinterpret_cast`. V tématu [C++ základní pokyny Type.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26491 NO_STATIC_DOWNCAST  
  Nepoužívejte `static_cast` downcasts. V tématu [C++ základní pokyny Type.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26492 NO_CONST_CAST  
  Nepoužívejte `const_cast` přetypovat rychle `const`. V tématu [C++ základní pokyny Type.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
    
C26493 NO_CSTYLE_CAST  
  Nepoužívejte přetypování ve stylu jazyka. V tématu [C++ základní pokyny Type.4](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type). 
     
C26494 VAR_USE_BEFORE_INIT  
  Proměnná % variable % není inicializován. Vždy inicializujte objekt. V tématu [C++ základní pokyny Type.5](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
C26495 MEMBER_UNINIT  
  Proměnná % variable % není inicializován. Vždy inicializace členské proměnné. V tématu [C++ základní pokyny Type.6](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-type).  
  
## <a name="bounds-group"></a>ROZSAH skupiny

[C26481 NO_POINTER_ARITHMETIC](C26481.md)   
  Nepoužívejte aritmetika ukazatele. Místo toho použijte rozpětí. V tématu [C++ základní pokyny Bounds.1](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
C26482 NO_DYNAMIC_ARRAY_INDEXING  
  Pouze index do polí pomocí konstantní výrazy. V tématu [C++ základní pokyny Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
C26483 STATIC_INDEX_OUT_OF_RANGE  
  Hodnota % hodnota je mimo rozsah (0, vázané % %) proměnné % variable %. Pouze index do polí pomocí konstantní výrazy, které jsou v rámci hranice pole. V tématu [C++ základní pokyny Bounds.2](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  

[C26485 NO_ARRAY_TO_POINTER_DECAY](C26485.md)   
  Výraz '% expr %': žádná pole pro decay ukazatel. V tématu [C++ základní pokyny Bounds.3](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md#SS-bounds).  
  
## <a name="see-also"></a>Viz také  
[Pomocí kameny pokyny základní C++](using-the-cpp-core-guidelines-checkers.md)
