---
title: IDebugProcessSecurity::GetUserName | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f8340e9fd9e5f38963a9de78e2974404f600deef
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56686168"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
Získá uživatelské jméno od dodavatele portu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetUserName(
    BSTR *pbstrUserName
);
```

```csharp
int GetUserName (
    string pbstrUserName
);
```

#### <a name="parameters"></a>Parametry
 `pbstrUserName`

 [out] Řetězec obsahující uživatelské jméno.

## <a name="return-value"></a>Návratová hodnota
 Pokud metoda uspěje, vrátí `S_OK`. V opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 `GetUserName` Vrátí uživatelské jméno, které se zobrazí **uživatelské jméno** sloupec **připojit k procesu** dialogové okno. Chcete-li zobrazit **připojit k procesu** dialogové okno, klikněte na tlačítko **připojit k procesu** na **nástroje** v nabídce [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).

## <a name="see-also"></a>Viz také
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)