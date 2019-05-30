---
title: IDebugProcess2::GetAttachedSessionName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::GetAttachedSessionName
helpviewer_keywords:
- IDebugProcess2::GetAttachedSessionName
ms.assetid: 7e5e116f-2c0c-4bc8-ad3f-e9fd2318a7e4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 1d14e76e576aaf3e467ab24083d445c9d9fc5214
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353153"
---
# <a name="idebugprocess2getattachedsessionname"></a>IDebugProcess2::GetAttachedSessionName
Získá název relace, která je ladění tohoto procesu. Integrované vývojové prostředí můžete zobrazit tyto informace pro uživatele, který se ladí konkrétní proces na daném počítači.

> [!NOTE]
> Tato metoda je zastaralá a jeho implementace by měla vždy vrátit `E_NOTIMPL`.

## <a name="syntax"></a>Syntaxe

```
HRESULT GetAttachedSessionName(
   BSTR* pbstrSessionName
);
```

## <a name="parameters"></a>Parametry
`pbstrSessionName`\

## <a name="return-value"></a>Návratová hodnota
 Tato metoda by měla vždy vrátit `E_NOTIMPL`.

## <a name="see-also"></a>Viz také:
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)