---
title: IDebugComPlusSymbolProvider | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugComPlusSymbolProvider interface
ms.assetid: 5b98e908-fd15-49a6-9010-933c9b948085
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: eee0fd9f65d09eff9593ee1932b9e713639c262f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56717907"
---
# <a name="idebugcomplussymbolprovider"></a>IDebugComPlusSymbolProvider
Představuje zprostředkovatele symbol modelu COM + s metodami, které jsou specifické pro spravovaný kód.

## <a name="syntax"></a>Syntaxe

```
IDebugComPlusSymbolProvider : IDebugSymbolProvider
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Ačkoli neexistuje nejsou nijak odděleny rozhraní, které jsou užitečné pro vyhodnocovače výrazů (EE) a ty, které jsou určeny k použití pomocí ladicího stroje (DE), následující metody se pravděpodobně zajímají DE vývojáři pouze: AreSymbolsLoaded GetAddressesInModuleFromPosition, GetEntryPoint, GetFunctionLineOffset, GetLocalVariableLayout, IsFunctionStale, LoadSymbols, LoadSymbolsFromStream, ReplaceSymbols, UnloadSymbols a UpdateSymbols.

## <a name="methods"></a>Metody
 Kromě metod na [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[AreSymbolsLoaded](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-aresymbolsloaded.md)|Určuje, pokud jsou načteny symboly ladění pro zadaný modul zadaný identifikátor domény aplikace.|
|[CreateTypeFromPrimitive](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-createtypefromprimitive.md)|Vytvoří typ z určeného primitivního typu.|
|[GetAddressesInModuleFromPosition](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getaddressesinmodulefromposition.md)|Pozice dokumentu v zadaném modulu se mapuje na pole adresy ladění.|
|[GetArrayTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getarraytypefromaddress.md)|Načte zadejte informace o zadané pole na základě daných jeho adresa pro ladění.|
|[GetAssemblyName](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getassemblyname.md)|Načte název sestavení zadané jeho modulu a aplikační domény.|
|[GetAttributedClassesForLanguage](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesforlanguage.md)|Načte tříd, které jsou implementovány v daném programovací jazyk pomocí zadaného atributu.|
|[GetAttributedClassesinModule](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getattributedclassesinmodule.md)|Načte třídy pomocí zadaného atributu v zadaném modulu.|
|[GetEntryPoint](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getentrypoint.md)|Načte vstupní bod aplikace.|
|[GetFunctionLineOffset](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getfunctionlineoffset.md)|Načte adresu v rámci funkce, která představuje posun daném řádku.|
|[GetLocalVariablelayout](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getlocalvariablelayout.md)|Načte rozložení lokální proměnné pro sadu metod.|
|[GetNameFromToken](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getnamefromtoken.md)|Vrátí název přidružený k zadaný token zadaný objekt jeho metadat.|
|[GetSymAttribute](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymattribute.md)|Načte symboly ladění s atributem daná nadřazená pro zadaný modul.|
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-getsymunmanagedreader.md)|Načte modul pro načítání symbolů pro nespravovaný kód.|
|[GetTypeFromAddress](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-gettypefromaddress.md)|Načte do typ symbolu zadané adresy ladění.|
|[IsFunctionDeleted](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctiondeleted.md)|Určuje, pokud je funkce na adrese zadaný ladění odstranila.|
|[IsFunctionStale](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-isfunctionstale.md)|Určuje, pokud funkci na adrese zadaný ladění se považuje za zastaralý.|
|[IsHiddenCode](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-ishiddencode.md)|Určuje, zda kód na adrese určený ladicí program je skrytý.|
|[LoadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbols.md)|Načte zadaný ladicí symboly v paměti.|
|[LoadSymbolsFromStream](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-loadsymbolsfromstream.md)|Načtení ladění symboly uvedené datového proudu.|
|[ReplaceSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-replacesymbols.md)|Nahradí aktuální symboly ladění programů v zadaného datového proudu.|
|[UnloadSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-unloadsymbols.md)|Uvolní symboly ladění pro zadaný modul z paměti.|
|[UpdateSymbols](../../../extensibility/debugger/reference/idebugcomplussymbolprovider-updatesymbols.md)|Aktualizuje symboly ladění v paměti s těmi na zadaný datový proud.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll