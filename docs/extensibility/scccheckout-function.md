---
title: Funkce SccCheckout | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccCheckout
helpviewer_keywords: SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: de22bd4722df1cd78472fd9e180fdb8132401828
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="scccheckout-function"></a>SccCheckout – funkce
Zadaný seznam názvů plně kvalifikovaný souborů, tato funkce rezervuje je na místní disk. Komentář platí pro všechny soubory, které jsou právě rezervována. Argument komentář může mít `null` řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 : %{nfiles/  
 [v] Počet souborů, které chcete rezervovat.  
  
 lpFileNames  
 [v] Pole názvy souborů rezervaci úplná místní cesta.  
  
 lpComment  
 [v] Komentář má být použita pro každou z vybraných souborů, které právě rezervována.  
  
 fOptions  
 [v] Příkaz příznaky (viz [bitové příznaky používané určité příkazy](../extensibility/bitflags-used-by-specific-commands.md)).  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Podívejte se na byla úspěšná.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není ve správě zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě. Soubor nebyl rezervován.|  
|SCC_E_ALREADYCHECKEDOUT|Uživatel už má soubor rezervovaný.|  
|SCC_E_FILEISLOCKED|Soubor je uzamčen, která zakazují vytvoření nových verzí.|  
|SCC_E_FILEOUTEXCLUSIVE|Jiný uživatel bylo dokončeno výhradní rezervaci u tohoto souboru.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Bitové příznaky, které používá konkrétní příkazy](../extensibility/bitflags-used-by-specific-commands.md)