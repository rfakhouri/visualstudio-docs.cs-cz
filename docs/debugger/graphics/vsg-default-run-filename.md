---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb56f7ef08241aed2e109e6845af8fb596cb42e4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711823"
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
Definuje výchozí název souboru pro soubor protokolu grafiky.

## <a name="syntax"></a>Syntaxe

```C++
#define VSG_DEFAULT_FILENAME filename
```

#### <a name="parameters"></a>Parametry
 `filename` Název souboru zadaný ve výchozím nastavení pro soubor protokolu grafiky při informací grafiky je zachycena prostřednictvím kódu programu.

## <a name="value"></a>Hodnota
 Řetězcový literál, který představuje název souboru grafiky souboru protokolu. Ve výchozím nastavení, L"default.vsglog".

```C++
#define VSG_DEFAULT_FILENAME L"default.vsglog"
```

## <a name="remarks"></a>Poznámky
 Pokud se symbol preprocesoru `DONT_SAVE_VSGLOG_TO_TEMP` je definován, pak název souboru je relativní vzhledem k aktuální adresář zachycené aplikace, nebo je absolutní cesta; v opačném případě je relativní k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.

 Chcete-li změnit název definovaný souboru, je třeba znovu definovat ho předtím, než zahrnete `vsgcapture.h` ve svém programu.

## <a name="example"></a>Příklad
 Tento příklad ukazuje, jak změnit výchozí název souboru zachytávací soubor:

```C++
// Redefine the default capture filename before including vsgcapture.h
#define VSG_DEFAULT_FILENAME L"capture.vsglog"

#include <vsgcapture.h>
```

## <a name="see-also"></a>Viz také
- [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)