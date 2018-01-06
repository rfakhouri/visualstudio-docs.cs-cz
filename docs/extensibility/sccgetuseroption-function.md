---
title: Funkce SccGetUserOption | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccGetUserOption
helpviewer_keywords: SccGetUserOption function
ms.assetid: 17863747-1901-4c53-a2b3-ed996085e120
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5c23e1fd5614963d8f52edc019e99287187fd9a3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetuseroption-function"></a>SccGetUserOption – funkce
Tato funkce načte různé možnosti specifické pro uživatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetUserOption(  
   LPVOID pContext,  
   LONG nOption,  
   LPLONG lpVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 nOption  
 [v] Možnost načíst (viz poznámky pro způsobů).  
  
 lpVal  
 [out] Hodnota přidružená možnost.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Možnost byl načteny.|  
|SCC_E_OPNOTSUPPORTED|Možnost není podporována.|  
|SCC_E_NONSPECIFICERROR|Došlo k neurčené chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Pomocí tohoto příkazu jsou podporovány následující možnosti:  
  
|Možnost uživatelů|Popis|  
|-----------------|-----------------|  
|`SCC_USEROPT_CHECKOUT_LOCALVER`|Určuje, jestli uživatel chce podívejte se na místní verzi souborů. `lpVal`je přiřazen `SCC_USEROPT_COLV_YES` (chce uživatel podívejte se na místní soubory) nebo `SCC_USEROPT_COLV_NO`.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Chybové kódy](../extensibility/error-codes.md)