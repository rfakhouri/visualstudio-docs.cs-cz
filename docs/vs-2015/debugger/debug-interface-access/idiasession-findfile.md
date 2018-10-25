---
title: Idiasession::FindFile – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d06d17607721f86d321c34253912dfa705aabd4
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49811708"
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte zdrojové soubory kompilace a název.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCompiland`  
 [in] [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt představující kompilantu se použije jako kontext pro hledání. Nastavte tento parametr na `NULL` k vyhledání zdrojových souborů ve všech souborech určených ke kompilaci.  
  
 `name`  
 [in] Určuje název zdrojového souboru, který se má načíst. Nastavte tento parametr na `NULL` pro všechny zdrojové soubory, které se mají načíst.  
  
 `option`  
 [in] Určení možností porovnání použitý k hledání názvu. Hodnoty z [namesearchoptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md) výčtu lze použít samostatně nebo v kombinaci.  
  
 `ppResult`  
 [out] Vrátí [idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md) načíst objekt, který obsahuje seznam zdrojových souborů.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
  
```cpp#  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumsourcefiles –](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions – výčet](../../debugger/debug-interface-access/namesearchoptions.md)



