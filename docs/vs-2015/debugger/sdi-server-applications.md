---
title: Aplikace serveru SDI | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- SDI server applications
- SDI server applications, debugging
ms.assetid: 09713718-1376-4753-b119-26f36639693e
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 1296c0f43d0409df0081861095c5ec068932bbc1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148151"
---
# <a name="sdi-server-applications"></a>Aplikace serveru SDI
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud ladíte aplikace serveru SDI, je nutné zadat `/Embedding` nebo `/Automation` v **argumenty příkazového řádku** vlastnost *projektu* dialogové okno stránky vlastností pro C/C++, C#, nebo Projekty Visual Basic.  
  
 S těmito argumenty příkazového řádku můžete ladicí program spuštění serverové aplikace, jako by byly spuštěny z kontejneru. Kontejner od programový manažer nebo správce souborového poté způsobí kontejneru pro použití instance serveru spuštěného v ladicím programu.  
  
## <a name="finding-the-command-line-arguments-property"></a>Vyhledání vlastnosti argumenty příkazového řádku  
 Pro přístup *projektu* dialogové okno stránky vlastností, klikněte pravým tlačítkem na projekt v Průzkumníku řešení a v místní nabídce zvolte možnost Vlastnosti. Pokud chcete najít vlastnost argumenty příkazového řádku, rozbalte kategorii vlastnosti konfigurace a klikněte na stránce ladění.  
  
## <a name="see-also"></a>Viz také  
 [COM a ActiveX ladění](../debugger/com-and-activex-debugging.md)   
 [Postupy: Ladění serverů modelu COM](../debugger/how-to-debug-com-servers.md)
