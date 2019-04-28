---
title: IDebugAlias2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugAlias2 interface
ms.assetid: 5252dcbb-8bfe-4d8a-a8e5-b022b194df19
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 951f0dde4dbd57ac18269adedd77c8f6d7ccdd5e
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63410094"
---
# <a name="idebugalias2"></a>IDebugAlias2
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Představuje číselná aliasu pro proměnnou a umožňuje vyhodnocovače výrazů (EE) k získání aliasu domény aplikace.

## <a name="syntax"></a>Syntaxe

```
IDebugAlias2 : IDebugAlias
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno modulem spravovaného ladění (DE).

## <a name="methods"></a>Metody
 Kromě metod na [IDebugAlias](../../../extensibility/debugger/reference/idebugalias.md) rozhraní, toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[GetAppDomainId](../../../extensibility/debugger/reference/idebugalias2-getappdomainid.md)|Načte identifikátor pro doménu aplikace.|

## <a name="remarks"></a>Poznámky
 Desetinné číslo ve formátu řetězce následované znakem #, například 1001# je alias.

## <a name="requirements"></a>Požadavky
 Záhlaví: EE.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll