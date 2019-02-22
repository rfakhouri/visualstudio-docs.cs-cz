---
title: IDebugProcess2::GetAttachedSessionName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: aa932817c796249803558ad1eb877f620198b3e4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56703538"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
Získá název relace, která je ladění tohoto procesu. Integrované vývojové prostředí můžete zobrazit tyto informace pro uživatele, který se ladí konkrétní proces na daném počítači.

> [!NOTE]
>  Tato metoda je zastaralá a jeho implementace by měla vždy vrátit `E_NOTIMPL`.

## <a name="syntax"></a>Syntaxe

```
HRESULT GetAttachedSessionName(
   BSTR* pbstrSessionName
);
```

#### <a name="parameters"></a>Parametry
 `pbstrSessionName`

## <a name="return-value"></a>Návratová hodnota
 Tato metoda by měla vždy vrátit `E_NOTIMPL`.

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)