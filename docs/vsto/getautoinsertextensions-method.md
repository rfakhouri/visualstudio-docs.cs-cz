---
title: Getautoinsertextensions – metoda
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: debe61f07a8aa8711f1bb0b75ff0c2b39a528b21
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54875833"
---
# <a name="getautoinsertextensions-method"></a>Getautoinsertextensions – metoda
  Získá informace o aplikacích pro Office, které se mají automaticky vložit během ladění.  
  
 Tato metoda je vyhrazená pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*psaExtensionNames*|Názvy rozšíření aplikace pro Office.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která označuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Každá aplikace pro Office, které má být vložen se vrátí jako název rozšíření aplikace Office, která odpovídá hodnotě v části **HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer**. Hostitel musí vyhledat tyto hodnoty v registru a automaticky vkládat rozšíření.  
