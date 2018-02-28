---
title: Funkce SccUninitialize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5976313939ee9efa81c71e7894da8e5f45e2d017
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccuninitialize-function"></a>SccUninitialize – funkce
Tato funkce vyčistíte žádné přidělení nebo otevřená připojení vytvořené z předchozího volání [SccInitialize](../extensibility/sccinitialize-function.md) v rámci přípravy vypínání modulu plug-in zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Ukazatel na strukturu zdroj ovládacího prvku modulu plug-in kontextu vytvořené v [SccInitialize](../extensibility/sccinitialize-function.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Vyčištění byla úspěšně dokončena.|  
  
## <a name="remarks"></a>Poznámky  
 Správa zdrojového kódu modul plug-in je zodpovědný při přípravě na vypnout a uvolnit paměť, která má modul plug-in přidělené pro strukturu kontextu. Tato funkce volána jednou pro každou instanci daného modulu plug-in. Volání [SccInitialize](../extensibility/sccinitialize-function.md) předchází toto volání. Nejsou žádné projekty může být stále otevřete v době volání `SccUninitialize`.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)