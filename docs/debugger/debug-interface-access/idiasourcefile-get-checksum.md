---
title: "Idiasourcefile::get_checksum – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSourceFile::get_checksum method
ms.assetid: aad63a7e-4e22-44e4-8a5b-81b5174ced1e
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3cc815608c1871de7269a432e02f95acbb3e0d81
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasourcefilegetchecksum"></a>IDiaSourceFile::get_checksum
Načte kontrolní součet bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_checksum (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cbData`  
 [v] Velikost vyrovnávací paměť dat v bajtech.  
  
 `pcbData`  
 [out] Vrátí počet bajtů kontrolního součtu. Tento parametr nemůže být `NULL`.  
  
 `data`  
 [ve out] Vyrovnávací paměť, která je vyplněn kontrolní součet bajtů. Pokud tento parametr je `NULL`, pak `pcbData` vrátí počet bajtů požadovaných.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li určit typ kontrolního součtu algoritmus, který byl použit ke generování bajtů kontrolního součtu, zavolejte [idiasourcefile::get_checksumtype –](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md) metoda.  
  
 Kontrolního součtu se obvykle generují z bitovou kopii zdrojového souboru, takže změny ve zdrojovém souboru se projeví v změny v bajtech kontrolního součtu. Pokud kontrolní součet bajtů neodpovídají žádné kontrolní součet generované z načíst bitové kopie souboru, potom by se měly zvažovat soubor poškozený nebo manipulováno.  
  
 Typické kontrolní součty jsou nikdy velikost víc než 32 bajtů, ale Nepředpokládejte, že je maximální velikost kontrolní součet. Nastavte `data` parametru `NULL` získat počet bajtů požadovaných k načtení kontrolního součtu. Potom přidělit vyrovnávací paměť odpovídající velikosti a volat tuto metodu jednou s novou vyrovnávací paměti.  
  
## <a name="see-also"></a>Viz také  
 [Idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSourceFile::get_checksumType](../../debugger/debug-interface-access/idiasourcefile-get-checksumtype.md)