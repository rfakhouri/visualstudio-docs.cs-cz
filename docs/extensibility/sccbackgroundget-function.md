---
title: Sccbackgroundget – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 51e1768e23eb61a5a6463d8d48f64683987f431a
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56707966"
---
# <a name="sccbackgroundget-function"></a>Sccbackgroundget – funkce
Tato funkce se načte ze správy zdrojového kódu každého ze zadaných souborů bez zásahu uživatele.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccBackgroundGet(
   LPVOID  pContext,
   LONG    nFiles,
   LPCSTR* lpFileNames,
   LONG    dwFlags,
   LONG    dwBackgroundOperationID
);
```

### <a name="parameters"></a>Parametry
 pContext

[in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.

 %{nfiles/

[in] Počet souborů podle `lpFileNames` pole.

 lpFileNames

[out v] Pole názvy souborů, které se mají načíst.

> [!NOTE]
>  Názvy musí být plně kvalifikovaný místní názvy souborů.

 dwFlags

[in] Příkaz příznaky (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).

 dwBackgroundOperationID

[in] Jedinečná hodnota přidružená k této operaci.

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Operace byla úspěšně dokončena.|
|SCC_E_BACKGROUNDGETINPROGRESS|Načítání na pozadí již probíhá (modul plug-in správy zdrojového kódu by měla vrátit to jenom v případě, že nepodporuje souběžné dávkové operace).|
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před probíhá její dokončování.|

## <a name="remarks"></a>Poznámky
 Tato funkce je volána vždy ve vlákně, která se liší od toho, který načten modul plug-in správy zdrojového kódu. Tato funkce se má vracet, dokud se provádí; může být však volána více než jednou s více seznamů soubory, všechny najednou.

 Použití `dwFlags` argument je stejné jako [sccget –](../extensibility/sccget-function.md).

## <a name="see-also"></a>Viz také:
- [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)
- [SccGet](../extensibility/sccget-function.md)