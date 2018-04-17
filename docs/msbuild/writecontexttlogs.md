---
title: WriteContextTLogs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
apiname:
- WriteContextTLogs
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- WriteContextTLogs
ms.assetid: ffc6c7be-3f22-4624-9ffc-0122fe72b6ec
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9cec743a1cca7ca9a5d9b428a16e3be4456d334b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="writecontexttlogs"></a>WriteContextTLogs
Zapíše soubory protokolů pro aktuální kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WINAPI WriteContextTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v] `intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [v] `tlogRootName`  
 Název kořenového názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [WriteAllTLogs](../msbuild/writealltlogs.md)