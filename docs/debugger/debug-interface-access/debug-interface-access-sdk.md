---
title: "Přístup k rozhraní SDK ladění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- debugging [DIA SDK]
- debugger [DIA SDK]
- DIA SDK
ms.assetid: 4c0abe53-11d3-4b7a-bdc7-b054f85aaf40
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: cd84741d006304f7dfefe8ee4a1060ba64ffdb8b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debug-interface-access-sdk"></a>Přístup k rozhraní ladění SDK
Microsoft ladění rozhraní přístup Software Development Kit (DIA SDK) poskytuje přístup k ladění informace uložené v souborech databáze (.pdb) program generované postcompiler nástroje společnosti Microsoft. Vzhledem k tomu, že formát souboru PDB generované nástroji postcompiler zde nevyskytlo konstantní revize, vystavení formát je nepraktické. Pomocí rozhraní API DIA, můžete vyvíjet aplikace, které vyhledávání a procházení ladicí informace uložené v souboru pdb. Tyto aplikace může například sestavy informace zpětným trasování zásobníku a analýza dat výkonu.  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Začínáme](../../debugger/debug-interface-access/getting-started-debug-interface-access-sdk.md)  
 Poskytuje přehled DIA SDK funkce a určuje, kde je nainstalován DIA SDK a také požadovaná hlavička a soubory knihovny.  
  
 [Dotazování na soubor .Pdb](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 Poskytuje pokyny o tom, jak použít rozhraní API DIA k dotazování na soubor .pdb.  
  
 [Symboly a značky symbolů](../../debugger/debug-interface-access/symbols-and-symbol-tags.md)  
 Popisuje, jak se v rozhraní API DIA používají symboly a značky symbolů.  
  
 [Referenční informace](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)  
 Obsahuje rozhraní, metody, výčty a struktury DIA rozhraní API.  
  
 [Dia2dump – ukázka](../../debugger/debug-interface-access/dia2dump-sample.md)  
 Ukazuje, jak používat rozhraní API DIA pro vyhledávání a procházení informace o ladění.  
  
 [Dia2dump.cpp – zdrojový soubor](../../debugger/debug-interface-access/dia2dump-cpp-source-file.md)  
 Zdrojový kód používá [dia2dump – ukázka](../../debugger/debug-interface-access/dia2dump-sample.md) k předvedení DIA rozhraní API.