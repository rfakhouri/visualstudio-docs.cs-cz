---
title: Funkce SccQueryInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5e2838709d7c2c2ad6e6b1eeef36c2cc0018a1a1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31138880"
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo – funkce
Tato funkce získává informace o stavu pro určitou sadu vybraných souborů ve správě zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccQueryInfo(  
   LPVOID  pvContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 : %{nfiles/  
 [v] Počet souborů zadaný v `lpFileNames` pole a délka `lpStatus` pole.  
  
 lpFileNames  
 [v] Pole názvy souborů, které má být dotazován.  
  
 lpStatus  
 [ve out] Pole, ve kterém modul plug-in správy zdroje vrací příznaky stav pro každý soubor. Další informace najdete v tématu [souboru stavový kód](../extensibility/file-status-code-enumerator.md).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dotaz byl úspěšný.|  
|SCC_E_ACCESSFAILURE|Došlo k potížím s přístupem do systému správy zdrojů, pravděpodobně způsobeno problémy sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_PROJNOTOPEN|Projekt není otevřen v části Správa zdrojového kódu.|  
|SCC_E_NONSPECIFICERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Pokud `lpFileName` je prázdný řetězec, v současné době není žádné informace o stavu aktualizace. Jinak je úplná cesta název souboru, pro který se mohl změnit informace o stavu.  
  
 Návratové pole může být bitová maska s `SCC_STATUS_xxxx` bits. Další informace najdete v tématu [souboru stavový kód](../extensibility/file-status-code-enumerator.md). Systému správy zdrojů nemusí podporovat všechny typy bit. Například pokud `SCC_STATUS_OUTOFDATE` není nabízí, je bit právě není nastaven.  
  
 Při použití této funkce rezervovat soubory, vezměte na vědomí následující `MSSCCI` požadavky na stav:  
  
-   `SCC_STATUS_OUTBYUSER` je nastavena, pokud má aktuální uživatel je rezervována soubor.  
  
-   `SCC_STATUS_CHECKEDOUT` Nelze nastavit, pokud `SCC_STATUS_OUTBYUSER` nastavena.  
  
-   `SCC_STATUS_CHECKEDOUT` je nastavený pouze, pokud soubor je rezervován do určené pracovní adresář.  
  
-   Pokud soubor je rezervován podle aktuálního uživatele do adresáře než pracovní adresář `SCC_STATUS_OUTBYUSER` nastavená, ale `SCC_STATUS_CHECKEDOUT` není.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Soubor stavový kód](../extensibility/file-status-code-enumerator.md)