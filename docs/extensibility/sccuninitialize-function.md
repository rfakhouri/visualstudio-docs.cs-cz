---
title: Sccuninitialize – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fae6cf7d86d57152446e8acc9e87a0fcbb3d12db
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56721833"
---
# <a name="sccuninitialize-function"></a>SccUninitialize – funkce
Tato funkce vyčistí všechny přidělení nebo otevřená připojení vytvořili podle předchozího volání [sccinitialize –](../extensibility/sccinitialize-function.md) při přípravě na vypínání modulu plug-in správy zdrojového kódu.

## <a name="syntax"></a>Syntaxe

```cpp
SCCRTN SccUninitialize (
   LPVOID pvContext
);
```

#### <a name="parameters"></a>Parametry
 pvContext

[in] V vytvoří ukazatel na strukturu modulu plug-in kontext zdrojového ovládacího prvku [sccinitialize –](../extensibility/sccinitialize-function.md).

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Hodnota|Popis|
|-----------|-----------------|
|SCC_OK|Vyčištění byla úspěšně dokončena.|

## <a name="remarks"></a>Poznámky
 Modul plug-in správy zdrojového kódu je zodpovídá za připravuje se vypnout a uvolnit paměť, která má modul plug-in přidělené pro strukturu kontext. Funkce se volá jednou pro každou instanci daného modulu plug-in. Volání [sccinitialize –](../extensibility/sccinitialize-function.md) předchází toto volání. Žádné projekty nadále možné otevřít v okamžiku volání `SccUninitialize`.

## <a name="see-also"></a>Viz také
- [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
- [SccInitialize](../extensibility/sccinitialize-function.md)