---
title: SymTagEnum | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: SymTagEnum enumeration
ms.assetid: 528a50cf-e13d-46ec-a98c-323d5d047de9
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9165059991e4b961fc995b96a0c285f28a1587b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="symtagenum"></a>SymTagEnum
Určuje typ symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum SymTagEnum {   
   SymTagNull,  
   SymTagExe,  
   SymTagCompiland,  
   SymTagCompilandDetails,  
   SymTagCompilandEnv,  
   SymTagFunction,  
   SymTagBlock,  
   SymTagData,  
   SymTagAnnotation,  
   SymTagLabel,  
   SymTagPublicSymbol,  
   SymTagUDT,  
   SymTagEnum,  
   SymTagFunctionType,  
   SymTagPointerType,  
   SymTagArrayType,   
   SymTagBaseType,   
   SymTagTypedef,   
   SymTagBaseClass,  
   SymTagFriend,  
   SymTagFunctionArgType,   
   SymTagFuncDebugStart,   
   SymTagFuncDebugEnd,  
   SymTagUsingNamespace,   
   SymTagVTableShape,  
   SymTagVTable,  
   SymTagCustom,  
   SymTagThunk,  
   SymTagCustomType,  
   SymTagManagedType,  
   SymTagDimension,  
   SymTagCallSite,  
   SymTagInlineSite,  
   SymTagBaseInterface,  
   SymTagVectorType,  
   SymTagMatrixType,  
   SymTagHLSLType  
};  
```  
  
## <a name="elements"></a>Elementy  
 `SymTagNull`  
 Určuje, zda je symbol nemá žádný typ.  
  
 `SymTagExe`  
 Označuje, že symbol je soubor s příponou .exe. Existuje pouze jeden `SymTagExe` symbol za úložiště symbolů. To slouží jako globální obor a nemá lexikální nadřazený.  
  
 `SymTagCompiland`  
 Určuje symbol kompilace pro jednotlivé komponenty kompilace úložiště symbolů. Pro nativní aplikace `SymTagCompiland` symboly odpovídají soubory objektů propojené do bitové kopie. Pro některé druhy Image Microsoft Intermediate Language (MSIL) je jedna kompilace na třídu.  
  
 `SymTagCompilandDetails`  
 Určuje, že symbol obsahuje rozšířené atributy souboru pro kompilaci. Načítání tyto vlastnosti může vyžadovat načítání kompilace symboly.  
  
 `SymTagCompilandEnv`  
 Označuje, že symbol je řetězec v prostředí definovaná pro souboru pro kompilaci.  
  
 `SymTagFunction`  
 Označuje, že symbol je funkce.  
  
 `SymTagBlock`  
 Označuje, že symbol je vnořený blok.  
  
 `SymTagData`  
 Označuje, že je symbol data.  
  
 `SymTagAnnotation`  
 Označuje, že symbol je pro kód poznámky. Podřízené objekty tohoto symbolu jsou řetězce, konstantní dat (`SymTagData`, `LocIsConstant`, `DataIsConstant`). Většina klientů Ignorovat tento symbol.  
  
 `SymTagLabel`  
 Označuje, že je symbol štítek.  
  
 `SymTagPublicSymbol`  
 Označuje, že symbol je veřejný symbol. Pro nativní aplikace je tento symbol externí symbolů COFF došlo při propojování bitovou kopii.  
  
 `SymTagUDT`  
 Označuje, že symbol je uživatelem definovaný typ (struktura, třídu nebo union).  
  
 `SymTagEnum`  
 Označuje, že symbol je výčet.  
  
 `SymTagFunctionType`  
 Označuje, že je symbol typu podpis funkce.  
  
 `SymTagPointerType`  
 Označuje, že symbol je ukazatel typu.  
  
 `SymTagArrayType`  
 Určuje, zda je symbol typu pole.  
  
 `SymTagBaseType`  
 Označuje, že symbol je základní typ.  
  
 `SymTagTypedef`  
 Určuje, zda je symbol `typedef`, který je alias pro jiný typ.  
  
 `SymTagBaseClass`  
 Označuje, že symbol je základní třída typu definovaný uživatelem.  
  
 `SymTagFriend`  
 Označuje, že je symbol friend typu definovaný uživatelem.  
  
 `SymTagFunctionArgType`  
 Označuje, že symbol je argument funkce.  
  
 `SymTagFuncDebugStart`  
 Označuje, že symbol je umístění end kód prologu funkce.  
  
 `SymTagFuncDebugEnd`  
 Označuje, že je symbol od umístění Kód epilogu funkce.  
  
 `SymTagUsingNamespace`  
 Označuje, že symbol je název oboru názvů, aktivní v aktuálním oboru.  
  
 `SymTagVTableShape`  
 Označuje, že symbol je popis virtuální tabulku.  
  
 `SymTagVTable`  
 Označuje, že symbol je ukazatel virtuální tabulku.  
  
 `SymTagCustom`  
 Označuje, že symbol je vlastní symbol a neinterpretuje DIA.  
  
 `SymTagThunk`  
 Označuje, že je symbol převodu, použít pro sdílení dat mezi 16bitová a 32bitová kódu.  
  
 `SymTagCustomType`  
 Označuje, že je symbol symbol vlastní kompilátoru.  
  
 `SymTagManagedType`  
 Označuje, že symbol je v metadatech.  
  
 `SymTagDimension`  
 Označuje, že je symbol FORTRAN vícerozměrné.  
  
 `SymTagCallSite`  
 Označuje, že symbol představuje webu volání.  
  
 `SymTagInlineSite`  
 Označuje, že symbol představuje vložené lokality.  
  
 `SymTagBaseInterface`  
 Označuje, že symbol je základní rozhraní.  
  
 `SymTagVectorType`  
 Označuje, že je symbol typu vektoru.  
  
 `SymTagMatrixType`  
 Označuje, že je symbol typu matice.  
  
 `SymTagHLSLType`  
 Označuje, že je symbol typu vysokou úroveň shaderu jazyk.  
  
## <a name="remarks"></a>Poznámky  
 Všechny symboly v rámci souboru ladění mít identifikační značky, který určuje typ symbolu.  
  
 Hodnoty v tento výčet jsou vráceny prostřednictvím volání [idiasymbol::get_symtag –](../../debugger/debug-interface-access/idiasymbol-get-symtag.md) metoda.  
  
 Hodnoty v tento výčet jsou předávány omezit obor vyhledávání typu konkrétní symbol následující metody:  
  
-   [IDiaSession::findSymbolByAddr](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)  
  
-   [IDiaSession::findSymbolByRVA](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)  
  
-   [IDiaSession::findSymbolByRVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)  
  
-   [IDiaSession::findSymbolByToken](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)  
  
-   [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)  
  
-   [IDiaSession::findSymbolByVAEx](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)  
  
-   [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
  
-   [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Lexikální hierarchie typů symbolů](../../debugger/debug-interface-access/lexical-hierarchy-of-symbol-types.md)   
 [Idiasession::findsymbolbyaddr –](../../debugger/debug-interface-access/idiasession-findsymbolbyaddr.md)   
 [Idiasession::findsymbolbyrva –](../../debugger/debug-interface-access/idiasession-findsymbolbyrva.md)   
 [Idiasession::findsymbolbyrvaex –](../../debugger/debug-interface-access/idiasession-findsymbolbyrvaex.md)   
 [Idiasession::findsymbolbytoken –](../../debugger/debug-interface-access/idiasession-findsymbolbytoken.md)   
 [Idiasession::findsymbolbyva –](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [Idiasession::findsymbolbyvaex –](../../debugger/debug-interface-access/idiasession-findsymbolbyvaex.md)   
 [Idiasession::findchildren –](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)