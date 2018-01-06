---
title: Funkce SccRename | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccRename
helpviewer_keywords: SccRename function
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 2fa3c891f1e963b40e34fb0f664bcf479730c20d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccrename-function"></a>SccRename – funkce
Tato funkce přejmenuje soubor v systému správy zdrojů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccRename(  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName,  
   LPCSTR lpNewName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpFileName  
 [v] Soubor plně kvalifikovaný název souboru je přejmenován.  
  
 lpNewName  
 [v] Plně kvalifikovaný název nové. Pokud cesta k adresáři se liší, pak soubor přesunula z jednoho podadresáře do jiného.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Přejmenování operace byla úspěšně dokončena.|  
|SCC_E_PROJNOTOPEN|Projekt není otevřen v části Správa zdrojového kódu.|  
|SCC_E_FILENOTCONTROLLED|Soubor není ve správě zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k dokončení této operace.|  
|SCC_E_COULDNOTCREATEPROJECT|Projekt nelze vytvořit jako součást procesu přejmenování.|  
|SCC_E_OPNOTPERFORMED|Operace nebyla provedena.|  
|SCC_E_NONSPECIFICERROR|Došlo k neurčené nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce slouží k přejmenování souboru nebo ho přesunout z jednoho umístění do druhého v systému správy zdrojů. Modul plug-in správy zdroje neměli přístup k souboru na disku. Je zodpovědností rozhraní IDE Přejmenování místního souboru.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)