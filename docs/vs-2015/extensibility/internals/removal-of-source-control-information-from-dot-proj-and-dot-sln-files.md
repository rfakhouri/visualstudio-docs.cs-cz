---
title: Odebrání informacích správy zdrojových kódů z. Proj a. Sln – soubory | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b7cdaeb02f77d3775096f840a513f68e531b1299
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199378"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>Odebrání informací o správě zdrojového kódu ze souborů .Proj a .Sln
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ve verzi 1.2 rozhraní API modulu Plug-in zdroje ovládacího prvku SCC informace jsou uloženy v MSSCCPRJ. SCC souboru. Výhodou MSSCCPRJ. Soubor SCC je, že není source SCC informace - nastavit tak, jako je tomu v souborů .proj a .sln.  
  
## <a name="version-12-changes"></a>Změny verze 1.2  
 Při řízení moduly plug-in zdrojového kódu, které jsou založeny na rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.1 informace o ovládacím prvku ukládána v projektu (souborů .proj) a soubory řešení (.sln). Umístění databáze informacích správy zdrojových kódů je určená AuxPath a konkrétní místo v databázi je určená název_projektu. Toto chování může způsobit problémy po větev, větve nebo operace kopírování, protože název_projektu by být obvykle neplatné po každé z těchto operací.  
  
 V rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.1, rozhraní IDE se používá ~ SAK soubory k detekci, jestli podporuje modul plug-in MSSCCPRJ. Metoda SCC ukládání informacích správy zdrojových kódů. Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.2 obsahuje novou funkci pro podporu MSSCCPRJ zjišťování. Soubor SCC bez použití ~ SAK souboru. Další informace najdete v tématu [úplného Oproštění od ~ SAK soubory](../../extensibility/internals/elimination-of-tilde-sak-files.md).  
  
## <a name="see-also"></a>Viz také  
 [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)
