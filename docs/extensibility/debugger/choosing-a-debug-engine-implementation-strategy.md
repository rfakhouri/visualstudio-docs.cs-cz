---
title: "Výběr strategie implementace modulu ladění | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: fae5211ac270832f07038faafbd6f5bc463d3944
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>Výběr strategie implementace modulu ladění
Architektura běhu použijte k určení strategie implementace ladění modulu (DE). Modul ladění mohou být vytvořeny v rámci procesu pro program, který má být vyladěnou, v rámci procesu sadě Visual Studio relace ladění manager (SDM) nebo mimo proces do obou z nich. Následující pokyny by měly pomoci vám vybrat mezi tyto tři strategie.  
  
## <a name="guidelines"></a>Pokyny  
 Když je možné pro DE být mimo proces SDM i program chcete ladit, obvykle neexistuje žádný důvod k tomu. Volání přes hranice procesu jsou relativně pomalé.  
  
 Ladění moduly jsou už zadané pro prostředí Win32 nativní run-time a běžné prostředí runtime jazyka. Pokud pro některou z těchto prostředí musí nahradit DE, je nutné vytvořit DE v rámci procesu s SDM.  
  
 Jinak můžete zvolit vytváření DE v procesu na SDM nebo v rámci procesu programu chcete ladit. Je důležité zvážit, jestli vyhodnocovací filtr výrazů z DE potřebuje rychlosti přístupu k úložišti symbol program a jestli úložiště symbolů může být načtena do paměti pro rychlý přístup. Zvažte také následující:  
  
-   Pokud nejsou k dispozici mnoho volání mezi vyhodnocovací filtr výrazů a úložiště symbolů, nebo pokud úložiště symbolů lze číst do paměťového prostoru SDM, vytvořte DE v proces SDM. Musíte se vrátit CLSID ladění stroje do SDM při připojování do vaší aplikace. SDM používá k vytvoření instance v procesu DE tento CLSID.  
  
-   Pokud je DE musí volat program, který má přístup k úložišti symbol, vytvořte DE v rámci procesu s programu. V takovém případě program vytvoří instanci DE.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)