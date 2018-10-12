---
title: Sccuninitialize – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccUninitialize
helpviewer_keywords:
- SccUninitialize function
ms.assetid: 17cf5337-d251-4422-bc96-93fe7d48f2ae
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4682d5d92349db85969f7477a36628ec621ca1d
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49282916"
---
# <a name="sccuninitialize-function"></a>SccUninitialize – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce vyčistí všechny přidělení nebo otevřená připojení vytvořili podle předchozího volání [sccinitialize –](../extensibility/sccinitialize-function.md) při přípravě na vypínání modulu plug-in správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccUninitialize (  
   LPVOID pvContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] V vytvoří ukazatel na strukturu modulu plug-in kontext zdrojového ovládacího prvku [sccinitialize –](../extensibility/sccinitialize-function.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Vyčištění byla úspěšně dokončena.|  
  
## <a name="remarks"></a>Poznámky  
 Modul plug-in správy zdrojového kódu je zodpovídá za připravuje se vypnout a uvolnit paměť, která má modul plug-in přidělené pro strukturu kontext. Funkce se volá jednou pro každou instanci daného modulu plug-in. Volání [sccinitialize –](../extensibility/sccinitialize-function.md) předchází toto volání. Žádné projekty nadále možné otevřít v okamžiku volání `SccUninitialize`.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccInitialize](../extensibility/sccinitialize-function.md)

