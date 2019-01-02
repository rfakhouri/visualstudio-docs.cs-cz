---
title: Aplikace serveru SDI | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ec4178fb23d84812d7258bac8384264bed9d4690
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53885051"
---
# <a name="sdi-server-applications"></a>Aplikace serveru SDI
Pokud ladíte aplikace serveru SDI, je nutné zadat `/Embedding` nebo `/Automation` v **argumenty příkazového řádku** vlastnost *projektu* dialogové okno stránky vlastností pro C/C++, C#, nebo Projekty Visual Basic.  
  
 S těmito argumenty příkazového řádku můžete ladicí program spuštění serverové aplikace, jako by byly spuštěny z kontejneru. Kontejner od programový manažer nebo správce souborového poté způsobí kontejneru pro použití instance serveru spuštěného v ladicím programu.  
  
## <a name="finding-the-command-line-arguments-property"></a>Vyhledání vlastnosti argumenty příkazového řádku  
 Pro přístup *projektu* dialogové okno stránky vlastností, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a v místní nabídce zvolte možnost Vlastnosti. Pokud chcete najít vlastnost argumenty příkazového řádku, rozbalte kategorii vlastnosti konfigurace a klikněte na stránce ladění.  
  
## <a name="see-also"></a>Viz také  
 [COM a ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [Postupy: Ladění serverů modelu COM](../debugger/how-to-debug-com-servers.md)