---
title: IDebugSymbolProviderDirect | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSymbolProviderDirect interface
ms.assetid: 872b04a8-70de-4ab5-aceb-684c81828545
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d546cae810d40a850bb3dd2758f2f659eecdd18e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56697423"
---
# <a name="idebugsymbolproviderdirect"></a>IDebugSymbolProviderDirect
Představuje zprostředkovatele symbol, který má přímý přístup do metadat a základní rozhraní symbol.

## <a name="syntax"></a>Syntaxe

```
IDebugSymbolProviderDirect: IUnknown
```

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetAppIDFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getappidfromaddress.md)|Načte identifikátor domény aplikace podle první adresy ladění.|
|[GetCurrentModulesInfo](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesinfo.md)|Načte informace o modulech ve skupině symbol.|
|[GetCurrentModulesState](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getcurrentmodulesstate.md)|Načte informace o skupině symbol, který poskytovatel symbolů je jejím členem.|
|[GetMetaDataImport](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmetadataimport.md)|Načte informace o import metadat.|
|[GetMethodFromAddress](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getmethodfromaddress.md)|Načte informace o metodě na adrese zadaný ladění.|
|[GetSymUnmanagedReader](../../../extensibility/debugger/reference/idebugsymbolproviderdirect-getsymunmanagedreader.md)|Načte modul pro načítání symbolů pro nespravovaný kód.|

## <a name="remarks"></a>Poznámky
 Toto rozhraní je možné použít místo většinu dalších rozhraní poskytovatele symbolů. Poskytuje přímý přístup k metadatům a `CorSym` rozhraní.

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll