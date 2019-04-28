---
title: Sccqueryinfo – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccQueryInfo
helpviewer_keywords:
- SccQueryInfo function
ms.assetid: 3973d336-a9b7-41a2-a4e6-bb8184a96aaf
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d2c17d20b54ea16f0a6764277855ca240aeb7224
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62433172"
---
# <a name="sccqueryinfo-function"></a>SccQueryInfo – funkce
Tato funkce načítá informace o stavu pro sadu vybraných souborů pod správou zdrojových kódů.

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

[in] Struktura kontext modulu plug-in zdroje ovládacího prvku.

 %{nfiles/

[in] Počet souborů podle `lpFileNames` pole a délky `lpStatus` pole.

 lpFileNames

[in] Pole názvy souborů, aby se dalo dotazovat.

 lpStatus

[out v] Pole, ve které modul plug-in správy zdrojového kódu vrátí stav příznaky pro každý soubor. Další informace najdete v tématu [souboru stavový kód](../extensibility/file-status-code-enumerator.md).

## <a name="return-value"></a>Návratová hodnota
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:

|Value|Popis|
|-----------|-----------------|
|SCC_OK|Dotaz byl úspěšný.|
|SCC_E_ACCESSFAILURE|Došlo k problému s přístupem do správy zdrojového kódu, pravděpodobně způsobeno problémy s sítě nebo kolize. Doporučuje se zkuste to znovu.|
|SCC_E_PROJNOTOPEN|Projekt není otevřen v rámci správy zdrojového kódu.|
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě.|

## <a name="remarks"></a>Poznámky
 Pokud `lpFileName` je prázdný řetězec, aktuálně nejsou k dispozici žádné informace o stavu aktualizace. V opačném případě je úplná cesta název souboru, pro který se mohl změnit informace o stavu.

 Vrácené pole může být bitová maska z `SCC_STATUS_xxxx` bits. Další informace najdete v tématu [souboru stavový kód](../extensibility/file-status-code-enumerator.md). Systém správy zdrojového kódu nemusí podporovat všechny typy bit. Například pokud `SCC_STATUS_OUTOFDATE` není dostupná, pouze není nastaven bit.

 Při použití této funkce rezervace souborů, pamatujte na Tyhle věci `MSSCCI` stav požadavky:

- `SCC_STATUS_OUTBYUSER` je nastavena pokud má aktuální uživatel rezervoval soubor.

- `SCC_STATUS_CHECKEDOUT` Nelze nastavit, pokud `SCC_STATUS_OUTBYUSER` nastavena.

- `SCC_STATUS_CHECKEDOUT` pouze při nastavený souboru je rezervován do určeným pracovního adresáře.

- Pokud soubor je rezervován aktuálním uživatelem do na jiný adresář než pracovní adresář `SCC_STATUS_OUTBYUSER` je nastavena, ale `SCC_STATUS_CHECKEDOUT` není.

## <a name="see-also"></a>Viz také
- [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)
- [Kód stavu souboru](../extensibility/file-status-code-enumerator.md)