---
title: WriteAllTLogs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
apiname: WriteAllTLogs
apilocation: filetracker.dll
apitype: COM
helpviewer_keywords: WriteAllTLogs
ms.assetid: 1fa3e10b-263c-4960-a9ad-485c02a7a872
caps.latest.revision: "5"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 7cd9965a5a521c4c1984792b0f10c809d3aafe86
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="writealltlogs"></a>WriteAllTLogs
Zapisuje protokoly sledování pro všechny vláken a kontexty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT WINAPI WriteAllTLogs(LPCTSTR intermediateDirectory, LPCTSTR tlogRootName);  
```  
  
#### <a name="parameters"></a>Parametry  
 [v]`intermediateDirectory`  
 Adresář, do které chcete uložit protokol sledování.  
  
 [v]`tlogRootName`  
 Název kořenového názvu souboru protokolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **úspěšné** nastaven bit, pokud kontext sledování se vytvořil.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** FileTracker.h  
  
## <a name="see-also"></a>Viz také  
 [WriteContextTLogs](../msbuild/writecontexttlogs.md)