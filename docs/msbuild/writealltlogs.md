---
title: WriteAllTLogs | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- WriteAllTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e9244081a228ebcca3c50bd4d4cd4a55acf97c8
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56641556"
---
# <a name="writealltlogs"></a>WriteAllTLogs
Zapisuje protokoly sledování pro všechna vlákna a kontext.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);
```

#### <a name="parameters"></a>Parametry
- [in] `intermediateDirectory` Adresáře, ve kterém k uložení protokolu sledování.

- [in] `tlogRootName` Název kořenového názvu souboru protokolu.

## <a name="return-value"></a>Návratová hodnota
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.

## <a name="requirements"></a>Požadavky
 **Záhlaví:** *FileTracker.h*

## <a name="see-also"></a>Viz také:
- [WriteContextTLogs](../msbuild/writecontexttlogs.md)