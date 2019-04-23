---
title: IDebugStackFrame2::GetLanguageInfo | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetLanguageInfo
helpviewer_keywords:
- IDebugStackFrame2::GetLanguageInfo
ms.assetid: 0e12fd92-f155-46a7-8272-cda279388cfb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3d0f5c17fc0dd12cf8ecb184b667880462548877
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60093277"
---
# <a name="idebugstackframe2getlanguageinfo"></a>IDebugStackFrame2::GetLanguageInfo
Získá jazyk přidružené k tento rámec zásobníku.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetLanguageInfo ( 
   BSTR* pbstrLanguage,
   GUID* pguidLanguage
);
```

```csharp
int GetLanguageInfo ( 
   ref string pbstrLanguage,
   ref Guid   pguidLanguage
);
```

#### <a name="parameters"></a>Parametry
 `pbstrLanguage`

 [out] Vrátí název jazyka, který implementuje metodu spojenou s rámce zásobníku.

 `pguidLanguage`

 [out] Vrátí `GUID` jazyka. Pro [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] jazyků, například následující mohou být vráceny:

- `guidVBScriptLang`

- `guidJScriptLang`

- `guidCPPLang`

- `guidVBLang`

- `guidSQLLang`

- `guidScriptLang`

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="see-also"></a>Viz také
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)