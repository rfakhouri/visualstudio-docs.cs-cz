---
title: Getautoinsertextensions – metoda | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 67f6bfcb0ee38acf9abb604f28fa95eeaa605fde
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions – metoda
  Získá informace o aplikacích pro Office, které se mají automaticky vložit během ladění.  
  
 Tato metoda je vyhrazena pro budoucí použití.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Popis|  
|---------------|-----------------|  
|*psaExtensionNames*|Názvy rozšíření aplikace pro Office.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Hodnota HRESULT, která určuje, zda metoda byla úspěšně dokončena.  
  
## <a name="remarks"></a>Poznámky  
 Každá aplikace pro Office má být vložen se vrátí jako název rozšíření aplikace Office, který odpovídá hodnotě pod HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer. Hostitel musí vyhledat tyto hodnoty v registru a automaticky vložit rozšíření.  
  
  