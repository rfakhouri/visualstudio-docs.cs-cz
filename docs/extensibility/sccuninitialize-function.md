---
title: Funkce SccUninitialize | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 41cb6b5cec0e0d9bb4c90cc284009ab7fc693912
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140492"
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