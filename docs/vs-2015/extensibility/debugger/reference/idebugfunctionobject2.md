---
title: IDebugFunctionObject2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFunctionObject2 interface
ms.assetid: 56b2fdff-146d-4138-a34c-59a9c65a3ddd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 972cc9af0453668e4d5393a00bb80f34e2594273
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63388443"
---
# <a name="idebugfunctionobject2"></a>IDebugFunctionObject2
> [!IMPORTANT]
> V sadě Visual Studio 2015 je zastaralý tímto způsobem implementace vyhodnocovače výrazů. Informace o implementace vyhodnocovače výrazů modulu CLR najdete v tématu [vyhodnocovače výrazů modulu CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) a [spravované ukázka Chyba při vyhodnocování výrazu](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).

 Představuje funkci a zvyšuje [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) rozhraní.

## <a name="syntax"></a>Syntaxe

```
IDebugFunctionObject2 : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Vyhodnocovače výrazů (EE) implementuje toto rozhraní k reprezentaci funkce.

## <a name="notes-for-callers"></a>Poznámky pro volající
 Metody tohoto rozhraní odložit u **IDebugFunctionObject** následujícími způsoby:

- **IDebugEvaluate** metoda přijímá příznaky.

- **CreateObject** metoda přijímá příznaky a vypršení časového limitu.

- **CreateStringObjectWithLength** metoda má délku.

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject2-createobject.md)|Vytvoří objekt, který používá konstruktor daným nastavením příznaků hodnocení a hodnotu časového limitu.|
|[CreateStringObjectWithLength](../../../extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength.md)|Vytvoří objekt string, který má zadanou délku.|
|[Evaluate](../../../extensibility/debugger/reference/idebugfunctionobject2-evaluate.md)|Volá funkci a vrátí výslednou hodnotu jako objekt.|

## <a name="requirements"></a>Požadavky
 Záhlaví: EE.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll