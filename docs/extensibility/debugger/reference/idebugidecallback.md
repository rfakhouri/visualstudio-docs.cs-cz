---
title: IDebugIDECallback | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugIDECallback interface
ms.assetid: 8d31adc0-1c44-4658-8d4f-f4b73e35f4a6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bdbc1cc5a8f7534f2ee11699d67b4128796602c6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63413988"
---
# <a name="idebugidecallback"></a>IDebugIDECallback
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Umožňuje vyhodnocovače výrazů (EE) pro zobrazení zprávy v okně výstupu ladicího programu.

## <a name="syntax"></a>Syntaxe

```
IDebugIDECallback : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto zpětné volání je implementováno spravovaného ladicího stroje.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Mohou být spotřebovány vyhodnocovače výrazů, aby odesílal výstup do okna výstup ladicího programu.

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následující metodu:

|Metoda|Popis|
|------------|-----------------|
|[DisplayMessage](../../../extensibility/debugger/reference/idebugidecallback-displaymessage.md)|Odešle určenou zprávu řetězec do okna výstup ladicího programu.|

## <a name="requirements"></a>Požadavky
 Záhlaví: EE.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll