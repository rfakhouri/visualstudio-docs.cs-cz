---
title: "Getautoinsertextensions – metoda | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a53148b0130dd05f3ffc3360a518f9b2b66002e7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  