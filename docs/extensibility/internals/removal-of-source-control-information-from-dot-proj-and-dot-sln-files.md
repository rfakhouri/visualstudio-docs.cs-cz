---
title: Odebrat informacích správy zdrojových kódů ze souborů .proj a .sln
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, .sln and .proj files
ms.assetid: 7b06883f-35de-41e2-9a9e-d3edba236f17
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 100de838eb1b205046d09d1149d78d3adba43b91
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66260815"
---
# <a name="removal-of-source-control-information-from-proj-and-sln-files"></a>Odebrání informací o správě zdrojového kódu ze souborů .Proj a .Sln
Ve verzi 1.2 rozhraní API modulu Plug-in zdroje ovládacího prvku SCC informace jsou uloženy v MSSCCPRJ. SCC souboru. Výhodou MSSCCPRJ. Soubor SCC je, že není source SCC informace - nastavit tak, jako je tomu v souborů .proj a .sln.

## <a name="version-12-changes"></a>Změny verze 1.2
 Při řízení moduly plug-in zdrojového kódu, které jsou založeny na rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.1 informace o ovládacím prvku ukládána v projektu (souborů .proj) a soubory řešení (.sln). Umístění databáze informacích správy zdrojových kódů je určená AuxPath a konkrétní místo v databázi je určená název_projektu. Toto chování může způsobit problémy po větev, větve nebo operace kopírování, protože název_projektu by být obvykle neplatné po každé z těchto operací.

 V rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.1, rozhraní IDE se používá ~ SAK soubory k detekci, jestli podporuje modul plug-in MSSCCPRJ. Metoda SCC ukládání informacích správy zdrojových kódů. Rozhraní API modulu Plug-in zdroje ovládacího prvku verze 1.2 obsahuje novou funkci pro podporu MSSCCPRJ zjišťování. Soubor SCC bez použití ~ SAK souboru. Další informace najdete v tématu [úplného Oproštění od ~ SAK soubory](../../extensibility/internals/elimination-of-tilde-sak-files.md).

## <a name="see-also"></a>Viz také
- [Co je nového v rozhraní API modulu plug-in správy zdrojového kódu ve verzi 1.2](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)