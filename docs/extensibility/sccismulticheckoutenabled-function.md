---
title: Funkce SccIsMultiCheckoutEnabled | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccIsMultiCheckoutEnabled
helpviewer_keywords:
- SccIsMultiCheckoutEnabled function
ms.assetid: 6721639d-e475-4766-81b5-ee40a280fc70
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: b04cd593bd631ba92545901ff289a9f8ed4f1822
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccismulticheckoutenabled-function"></a>SccIsMultiCheckoutEnabled – funkce
Tato funkce zkontroluje, zda modul plug-in zdrojového kódu umožňuje více rezervace na soubor.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccIsMultiCheckoutEnabled(  
   LPVOID pContext,  
   LPBOOL pbMultiCheckout  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 pbMultiCheckout  
 [out] Určuje, zda je povoleno více rezervace pro tento projekt (nenulové hodnoty znamená, že se podporují více rezervace).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Kontrola byla úspěšná.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Prostředí IDE díky dvěma kontroly k určení, pokud soubory rezervací současně víc než jeden uživatel. Nejprve správy zdrojového kódu musí podporovat více rezervace. Správa zdrojového kódu modul plug-in můžete zadat tato funkce během inicializace zadáním `SCC_CAP_MULTICHECKOUT`. Prostředí IDE jako druhý kontrolu, následně volá této funkci můžete zjistit, zda aktuální projekt podporuje více rezervace. Pokud jsou pro vybraný projekt podporován více rezervace, modul plug-in vrátí a úspěch kód a nastaví `pbMultiCheckout` na nenulové hodnoty (`TRUE`) nebo `FALSE`.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)