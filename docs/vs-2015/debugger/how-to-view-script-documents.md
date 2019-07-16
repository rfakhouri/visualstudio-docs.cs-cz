---
title: 'Postupy: Zobrazení dokumentů skriptu | Dokumentace Microsoftu'
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
- Script Explorer
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
caps.latest.revision: 25
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 88f923ab0447f1ac7d57e84d94f0ab442d912d67
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68189592"
---
# <a name="how-to-view-script-documents"></a>Postupy: Zobrazení dokumentů skriptu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V dřívějších verzích [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], skript na straně klienta soubory vygenerované ze skriptu na straně serveru se zobrazily v okně Průzkumník skriptů. Okno Průzkumníka skriptu se často skrytý, aby dostupnosti skriptů na straně klienta nebyl vždy jasné.  
  
 V [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], skript na straně klienta soubory vygenerované ze skriptu na straně serveru se zobrazí v Průzkumníku řešení, který se zobrazí ve výchozím nastavení. V okně Průzkumník skriptů se odstranilo.  
  
 Soubory skriptu na straně klienta jsou viditelné pouze v případě, že jsou v režimu ladění nebo v režimu pozastavení. Zobrazí se v **dokumenty skriptu** uzlu.  
  
 Soubory skriptu na straně serveru jsou vždy viditelné. Zobrazí se v  **\<webu cesta >** uzlu. Název uzlu vypadá podobně jako v tomto příkladu: `c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>Chcete-li zobrazit dokument skriptu na straně serveru  
  
1. V **Průzkumníka řešení**, otevřete  **\<webu cesta >** uzlu.  
  
2. Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Soubor skriptu na straně serveru se otevře v okně zdroje.  
  
### <a name="to-view-a-client-side-script-document"></a>Chcete-li zobrazit dokument skriptu na straně klienta  
  
1. V **Průzkumníka řešení**, otevřete **dokumenty skriptu** uzlu.  
  
2. Poklikejte na soubor skriptu, který chcete zobrazit.  
  
     Soubor skriptu na straně klienta se otevře v okně zdroje.  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení dat v ladicím programu](../debugger/viewing-data-in-the-debugger.md)
