---
title: ResumeTracking | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- ResumeTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- ResumeTracking
ms.assetid: d637e019-7c50-4b0a-812e-bc822001e697
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f0bc04dfa06672e7764676be87584c2a757a50b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54940580"
---
# <a name="resumetracking"></a>ResumeTracking
Obnoví sledování v rámci aktuálního kontextu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WINAPI ResumeTracking();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 **HRESULT** s **SUCCEEDED** sadu bitů, pokud bylo obnoveno sledování. **E_FAIL** je vrácena, pokud sledování nelze obnovit, protože kontext nebyl dostupný.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** *FileTracker.h*  
  
## <a name="see-also"></a>Viz také:  
 [SuspendTracking](../msbuild/suspendtracking.md)