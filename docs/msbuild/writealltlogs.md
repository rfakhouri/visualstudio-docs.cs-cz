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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4ca5bfbdae319aff8d90686deb32a5c7348fa74e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985534"
---
# <a name="writealltlogs"></a>WriteAllTLogs
Zapisuje protokoly sledování pro všechna vlákna a kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [in] `intermediateDirectory`  
 Adresáře, ve kterém k uložení protokolu sledování.  
  
 [in] `tlogRootName`  
 Název kořenového názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud byl vytvořen kontext sledování.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *FileTracker.h*  
  
## <a name="see-also"></a>Viz také:  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)