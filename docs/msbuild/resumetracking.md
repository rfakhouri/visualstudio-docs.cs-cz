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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9608ca6237a44d48d4ee4c4d8daf057d88fc5b53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947827"
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