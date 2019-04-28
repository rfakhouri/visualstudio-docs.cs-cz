---
title: IRemoteDebugApplicationEx:GetHostPid | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:GetHostPid
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:GetHostPid
ms.assetid: 4cf9f46c-29cf-4201-87f0-5b1ddbed2f2b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d660cce006e7f84f1b1c01f1ec0a406b5c4b9df3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62934591"
---
# <a name="iremotedebugapplicationexgethostpid"></a>IRemoteDebugApplicationEx:GetHostPid

Vrátí ID procesu pro hostitelskou aplikaci.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetHostPid(
   DWORD*  dwHostPid
);
```

### <a name="parameters"></a>Parametry

`dwHostPid`

[out] Identifikátor procesu hostitele.

## <a name="return-value"></a>Návratová hodnota

Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.

|Hodnota|Popis|
|-----------|-----------------|
|`S_OK`|Metoda byla úspěšná.|

## <a name="remarks"></a>Poznámky

Použít integrovaného vývojového prostředí.

## <a name="see-also"></a>Viz také:

- [IRemoteDebugApplicationEx – rozhraní](iremotedebugapplicationex-interface.md)