---
title: Funkce SccAddFromScc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccAddFromScc
helpviewer_keywords:
- SccAddFromScc function
ms.assetid: 902e764d-200e-46e1-8c42-4da7b037f9a0
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ce2d9d179fd46bcc63340c911437486e1a459195
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccaddfromscc-function"></a>SccAddFromScc – funkce
Tato funkce umožňuje uživatelům procházet soubory, které jsou již v systému správy zdrojového kódu a následně Zkontrolujte tyto soubory součástí aktuálního projektu. Například můžete tuto funkci získat běžné hlavičkový soubor do aktuálního projektu bez kopírování souboru. Pole návratový souborů, `lplpFileNames`, obsahuje seznam souborů, které chce uživatel přidat do projektu IDE.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccAddFromScc (  
   LPVOID   pvContext,  
   HWND     hWnd,  
   LPLONG   lpnFiles,  
   LPCSTR** lplpFileNames  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpnFiles  
 [ve out] Vyrovnávací paměť pro počet souborů, které se přidávají v. (Toto je `NULL` pokud paměť na kterou odkazuje `lplpFileNames` se uvolnit. Podrobnosti najdete v části poznámky.)  
  
 lplpFileNames  
 [ve out] Pole ukazatele na všechny názvy souborů bez cesty adresářů. Toto pole je přiřadit a uvolnit pomocí modulu plug-in zdrojového kódu. Pokud `lpnFiles` = 1 a `lplpFileNames` není `NULL`, první název v poli, na kterou odkazuje `lplpFileNames` obsahuje cílovou složku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Soubory byly úspěšně nachází a přidat do projektu.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena s žádný vliv.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
  
## <a name="remarks"></a>Poznámky  
 Prostředí IDE volá tuto funkci. Pokud modul plug-in zdrojového kódu podporuje určení místní cílovou složku, předá prostředí IDE `lpnFiles` = 1 a předá název místní složky do `lplpFileNames`.  
  
 Při volání `SccAddFromScc` funkce vrátí, modul plug-in jeho přiřazení hodnoty k `lpnFiles` a `lplpFileNames`, přidělování paměti pro pole název souboru podle potřeby (Všimněte si, že toto přidělení nahrazuje ukazatel v `lplpFileNames`). Správa zdrojového kódu modul plug-in je zodpovědný za umístění všech souborů do adresáře uživatele nebo ve složce zadané označení. Prostředí IDE potom přidá soubory do projektu IDE.  
  
 Nakonec IDE volání této funkce podruhé, předávání v `NULL` pro `lpnFiles`. To je interpretovat jako speciální signál k uvolnění je paměť přidělená pro pole název souboru v modulu plug-in zdrojového kódu `lplpFileNames``.`  
  
 `lplpFileNames` je `char ***` ukazatel. Modul plug-in správy zdroje umístí ukazatel na pole ukazatele na názvy souborů, proto předávání seznamu v standardním způsobem pro toto rozhraní API.  
  
> [!NOTE]
>  Počáteční verze rozhraní API VSSCI neposkytnul způsob, jak vyjádřit cíl projektu přidané soubory. Pro uložení tohoto sémantika `lplpFIleNames` parametr vylepšené a nastavit jej jako vstup/výstup parametru spíše než výstupní parametr. Pokud jenom jeden soubor je zadán, který je hodnota na kterou odkazuje `lpnFiles` = 1, pak první prvek `lplpFileNames` obsahuje cílové složky. Použít tyto nové sémantiku IDE volání `SccSetOption` fungovat s `nOption`parametr nastaven na `SCC_OPT_SHARESUBPROJ`. Pokud modul plug-in správy zdroje nepodporuje sémantiky, vrátí `SCC_E_OPTNOTSUPPORTED`. Díky tomu tak zakáže použití **přidat od správy zdrojového kódu** funkce. Pokud modul plug-in podporuje **přidat od správy zdrojového kódu** funkce (`SCC_CAP_ADDFROMSCC`), pak musí podporovat nové sémantiku a vrátí `SCC_I_SHARESUBPROJOK`.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccSetOption](../extensibility/sccsetoption-function.md)