---
title: Funkce SccGet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccGet
helpviewer_keywords:
- SccGet function
ms.assetid: 09a18bd2-b788-411a-9da6-067d806e46f6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fb793eb5c35c4ca9ee22a58496ebe175b83c68e4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccget-function"></a>SccGet – funkce
Tato funkce načte kopii jeden nebo více souborů pro zobrazování a kompilování, ale ne pro úpravy. Ve většině systémů jsou soubory označené jako jen pro čtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccGet(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura kontextu modulu plug-in zdrojového kódu.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 : %{nfiles/  
 [v] Počet souborů zadaný v `lpFileNames` pole.  
  
 lpFileNames  
 [v] Pole plně kvalifikované názvy souborů, které mají být načteny.  
  
 fOptions  
 [v] Příkaz příznaky (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Úspěch operaci get.|  
|SCC_E_FILENOTCONTROLLED|Soubor není ve správě zdrojového kódu.|  
|SCC_E_OPNOTSUPPORTED|Správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_FILEISCHECKEDOUT|Nelze načíst soubor, který uživatel právě má rezervována.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NOSPECIFIEDVERSION|Zadali jste neplatný verze nebo datum a čas.|  
|SCC_E_NONSPECIFICERROR|Nespecifikované chybě; Soubor nebyl synchronizován.|  
|SCC_I_OPERATIONCANCELED|Operace zrušena před dokončením.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k provedení této operace.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je volána s počet a pole názvy souborů, které mají být načteny. Pokud IDE předá příznak `SCC_GET_ALL`, to znamená, že položky v `lpFileNames` nejsou soubory ale adresáře a že jsou všechny soubory ve správě zdrojového kódu v adresáři pro danou mají být načteny.  
  
 `SCC_GET_ALL` Příznak mohou být kombinovány s `SCC_GET_RECURSIVE` příznak načíst všechny soubory v adresáři pro danou a také všechny podadresáře.  
  
> [!NOTE]
>  `SCC_GET_RECURSIVE` mají být předány nikdy bez `SCC_GET_ALL`. Všimněte si také, že pokud adresářů C:\A a C:\A\B obě předaná na rekurzivního získat, C:\A\B a všechny jeho podadresáře se ve skutečnosti načíst dvakrát. Prostředí IDE odpovídá – a není zdroji řídit plug-in – zajistit, aby byly průběžně duplicitní položky, jako je tato mimo pole.  
  
 Nakonec i v případě, že zdroj řízení modulu plug-in zadaný `SCC_CAP_GET_NOUI` příznak při inicializaci, která určuje, že nemá uživatelské rozhraní pro příkaz Get, tuto funkci lze volat stále zařízení IDE se budou načítat soubory. Příznak jednoduše znamená, že rozhraní IDE nezobrazí položku nabídky Get a že modulu plug-in se očekává poskytování uživatelské rozhraní.  
  
## <a name="renaming-and-sccget"></a>Přejmenování a SccGet  
 Situace: uživatel rezervuje soubor, například a.txt a změní ho. Před a.txt mohou být vráceny se změnami, druhý uživatel přejmenuje a.txt na b.txt v databázi pro správu zdrojů, zkontrolujte b.txt, díky určité změny pro soubor a zkontroluje soubor. První uživatel chce, aby se změny provedené druhý uživatel tak, aby první uživatel přejmenuje jejich místní verzi souboru a.txt na b.txt a nemá get na soubor. Místní mezipaměti, která uchovává informace o čísla verzí, ale stále domnívá první verze součásti a.txt ukládají se místně a proto zdrojového kódu nemůže vyřešit rozdíly.  
  
 Existují dva způsoby, jak vyřešit tuto situaci, kde bude synchronizován s zdrojové databáze řízení místní mezipaměti zdroj řízení verzí:  
  
1.  Nepovolit přejmenování souboru v databázi zdrojové ovládací prvek, který je právě rezervována.  
  
2.  To ekvivalentem "odstranit staré" následované "Přidat nové". Následujícím algoritmu je jedním ze způsobů toho chcete dosáhnout.  
  
    1.  Volání [SccQueryChanges](../extensibility/sccquerychanges-function.md) funkce Další informace o přejmenování a.txt k b.txt v databázi zdrojové ovládacího prvku.  
  
    2.  Přejmenujte místní a.txt b.txt.  
  
    3.  Volání `SccGet` funkce pro a.txt i b.txt.  
  
    4.  Protože a.txt neexistuje v databázi pro správu zdrojů, místní verze mezipaměti se vyprazdňují chybějící a.txt informace o verzi.  
  
    5.  Soubor b.txt rezervován je sloučen s obsahem souboru místní b.txt.  
  
    6.  Aktualizované b.txt soubor může být nyní změnami.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Příznaky bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md)