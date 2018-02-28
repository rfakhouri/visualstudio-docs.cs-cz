---
title: Funkce SccGetEvents | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccGetEvents
helpviewer_keywords:
- SccGetEvents function
ms.assetid: 32f8147d-6dcc-465e-b07b-42da5824f9b0
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: e2e9a22d0340774087fab8dd7dc564f415d9d9aa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccgetevents-function"></a>SccGetEvents – funkce
Tato funkce načte událostí ve frontě stavu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGetEvents (  
   LPVOID pvContext,  
   LPSTR  lpFileName,  
   LPLONG lpStatus,  
   LPLONG pnEventsRemaining  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 lpFileName  
 [ve out] Vyrovnávací paměť, kde modul plug-in zdrojového kódu vloží název vráceného souboru (maximálně _max_path – znaků).  
  
 lpStatus  
 [ve out] Vrátí stavový kód (viz [souboru stavový kód](../extensibility/file-status-code-enumerator.md) pro možné hodnoty).  
  
 pnEventsRemaining  
 [ve out] Vrátí počet položek ponecháno ve frontě po toto volání. Pokud toto číslo velká, volající rozhodnout pro volání [SccQueryInfo](../extensibility/sccqueryinfo-function.md) získání všech informací o najednou.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Získání událostí bylo úspěšné.|  
|SCC_E_OPNOTSUPPORTED|Tato funkce není podporována.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je volána při nečinnosti zpracování zobrazíte, zda nedošlo k žádné aktualizací stavu pro soubory ve správě zdrojového kódu. Modul plug-in správy zdroje udržuje stav všechny soubory, které bude vědět o a při každé změně stavu je uvedeno pomocí modulu plug-in, stav a přidružený soubor jsou uložené ve frontě. Když `SccGetEvents` nazývá horní prvek fronty je načíst a vrácena. Tato funkce je omezená na vrací pouze informace uložené v mezipaměti a musí mít velmi rychlost (tedy bez čtení disku nebo žádostí o stav správy zdrojového kódu); v opačném případě může snižovat spustit výkon rozhraní IDE.  
  
 Pokud není žádná aktualizace stavu do sestavy, modul plug-in správy zdroje ukládá do vyrovnávací paměti, na kterou odkazuje prázdný řetězec `lpFileName`. Modul plug-in, jinak hodnota ukládá úplnou cestu souboru pro které informace o stavu došlo ke změně a vrátí odpovídající stavový kód (jedna z hodnot podrobně [souboru stavový kód](../extensibility/file-status-code-enumerator.md)).  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Soubor stavový kód](../extensibility/file-status-code-enumerator.md)