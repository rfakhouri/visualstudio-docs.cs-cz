---
title: Debug Interface Access SDK | Dokumentace Microsoftu
ms.date: 07/24/2018
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [DIA SDK]
- debugger [DIA SDK]
- DIA SDK
ms.assetid: 4c0abe53-11d3-4b7a-bdc7-b054f85aaf40
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bdc5a980c9019fdaf330db9602f0b8445456c7c4
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53889563"
---
# <a name="debug-interface-access-sdk"></a>Přístup k rozhraní ladění SDK

Microsoft ladění rozhraní přístup Software Development Kit (DIA SDK) poskytuje přístup k ladění informací uložených v generovaných postcompiler nástroje Microsoft soubory databáze (PDB) programu. Vzhledem k tomu, že formát souboru .pdb generovaných postcompiler nástroje podroben revizi konstantní, vystavení formát je nepraktické. Pomocí rozhraní API DIA, můžete vyvíjet aplikace, které vyhledávání a procházení ladicí informace uložené v souboru pdb. Tyto aplikace může například sestavy informace o zásobníku trasování zpět a analyzovat data o výkonu.

## <a name="in-this-section"></a>V tomto oddílu

[Začínáme](../../debugger/debug-interface-access/getting-started-debug-interface-access-sdk.md)  
Poskytuje přehled o DIA SDK funkcí a určuje, kde je nainstalován DIA SDK a požadované záhlaví nebo soubory knihoven.

[Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
Obsahuje pokyny k používání rozhraní API DIA k dotazování na soubor .pdb.

[Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)  
Popisuje, jak se v rozhraní API DIA používají symboly a značky symbolů.

[Referenční informace](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)  
Obsahuje rozhraní, metody, výčty a struktury DIA rozhraní API.

[Dia2dump – ukázka](../../debugger/debug-interface-access/dia2dump-sample.md)  
Ukazuje, jak použít rozhraní API DIA k vyhledávání a procházení ladicí informace.
